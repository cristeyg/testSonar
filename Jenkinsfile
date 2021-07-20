pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                    sh 'echo "Step One build something else" '
                }
            }
            stage('SonarQube') {
                steps {
                    sh 'echo "Step Two Sonarqube x" '
                }
            } 

            stage('Testing') {
                steps {
                    sh 'echo "Step Three dddtry" '
                }
            }

            stage('Deploy') {
                steps {
                    sh 'echo "Step Three" '
                }
            }
           stage('SonarQube analysis') {
                steps{
                    script {
                        scannerHome = tool 'SonarQube';
                    }
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                       -Dsonar.projectKey=Analisis1 \
                       -Dsonar.sources=. \
                       -Dsonar.css.node=. \
                    }
                }
            }
        }
}
