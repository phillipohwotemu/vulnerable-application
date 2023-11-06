pipeline {
    agent any
    tools {
        maven 'maven_3_5_2'
    }
    stages {
        stage('Set JAVA_HOME') {
            steps {
                script {
                    def jdkHome = tool name: 'JDK 8', type: 'jdk'
                    env.JAVA_HOME = "${jdkHome}/bin"
                    env.PATH = "${env.JAVA_HOME}:${env.PATH}"
                }
            }
        }
        stage('CompileandRunSonarAnalysis') {
            steps {
                sh 'mvn clean verify sonar:sonar -Dsonar.projectkey=wizebird -Dsonar.organization=wizebird -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a'
            }
        }
    }
}
