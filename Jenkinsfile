pipeline {
    agent any
    tools {
        maven 'maven_3_5_2'
    }
    stages {
        stage('CompileandRunSonarAnalysis') {
            steps {
                script {
                    sh 'env' // Print environment variables for debugging
                    def mvnCmd = 'mvn clean verify sonar:sonar ' +
                                 '-Dsonar.projectKey=wizebird ' +
                                 '-Dsonar.organization=wizebird ' +
                                 '-Dsonar.host.url=https://sonarcloud.io ' +
                                 '-Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a'
                    sh mvnCmd
                }
            }
        }
    }
}
