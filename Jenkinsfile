pipeline {
    agent any
    environment {
        // Define your JAVA_HOME environment variable
        JAVA_HOME = '/usr/lib/jvm/java-1.8.0-amazon-corretto'
    }
    tools {
        // Define the Maven tool
        maven 'maven_3_5_2'
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from Git
                checkout scm
            }
        }
        stage('Build and Analyze') {
            steps {
                // Compile and run SonarQube analysis
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
