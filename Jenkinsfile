pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-1.8.0-openjdk-amd64'
    }
    tools {
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
