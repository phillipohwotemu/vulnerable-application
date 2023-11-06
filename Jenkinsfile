pipeline {
    any agent
    tools {
        Maven 'maven_3_5_2'
    }
    stages{
        stage('CompileandRunSonarAnalysis') {
            steps {
                sh 'mvn clean verify sonar: -Dsonar.projectkey=kloud45 -Dsonar.organization=kloud45 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=a3c6729c99118b3abc0a7f2beb5cb2b817ac0b18'
            }
        }
    }
}
