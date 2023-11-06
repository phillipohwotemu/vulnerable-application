pipeline {
    agent any

    tools {
        // Specify the name of the JDK added in Jenkins
        jdk 'java 8'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Analyze') {
            steps {
                script {
                    sh '''
                    mvn clean verify sonar:sonar \
                        -Dsonar.projectKey=wizebird \
                        -Dsonar.organization=wizebird \
                        -Dsonar.host.url=https://sonarcloud.io \
                        -Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a
                    '''
                }
            }
        }
    }
}
