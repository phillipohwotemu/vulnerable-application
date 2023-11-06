pipeline {
    agent any
    environment {
        JAVA_HOME = '/path/to/java8' // Set the path to your JDK 8 installation
    }
    stages {
        stage('CompileandRunSonarAnalysis') {
            steps {
                sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=wizebird -Dsonar.organization=wizebird -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a'
            }
        }
    }
}

