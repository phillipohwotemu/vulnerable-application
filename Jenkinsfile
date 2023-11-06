pipeline {
    agent any
    tools {
        // Specify the JDK tool name you configured in Global Tool Configuration
        jdk 'JDK 8'
        maven 'maven_3_5_2'
    }
    stages {
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
