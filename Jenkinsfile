pipeline {
    agent any

    environment {
       
        SONAR_HOST_URL = 'http://34.69.251.47:9000'

        SONAR_TOKEN    = credentials('sonarqube-token')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }
    }

        stage('SonarQube Analysis') {
            steps {
                sh """
                    sonar-scanner \
                      -Dsonar.host.url=${SONAR_HOST_URL} \
                      -Dsonar.login=${SONAR_TOKEN} \
                      -Dsonar.projectKey=your-project-key \
                      -Dsonar.sources=. \
                      -Dsonar.sourceEncoding=UTF-8
                """
            }
        }
    }
}
