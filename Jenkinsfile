pipeline {
    agent any
    tools {
        jdk 'JDK 8' // Use the JDK 8 installation configured in Jenkins
        maven 'maven_3_5_2'
    }
    stages {
        stage('CompileandRunSonarAnalysis') {
            steps {
                sh 'mvn clean verify sonar:sonar -Dsonar.projectkey=wizebird -Dsonar.organization=wizebird -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a'
            }
        }
    }
}
