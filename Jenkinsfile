pipeline {
    agent any
    tools {
        jdk 'Java 8'
        maven 'maven_3_5_2'
    }
    stages {
        stage('Debug Environment') {
            steps {
                script {
                    echo "JAVA_HOME: ${env.JAVA_HOME}"
                    echo "PATH: ${env.PATH}"
                }
            }
        }
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build and Analyze') {
            steps {
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
