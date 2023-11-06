pipeline {
    agent any

    tools {
        // Specify the name of the JDK added in Jenkins
        Java 8 '/usr/lib/jvm/java-1.8.0-amazon-corretto'
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
