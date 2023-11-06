pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Analyze') {
            steps {
                script {
                    // Specify the name of the existing JDK installation
                    def jdk = tool name: '/usr/lib/jvm/java-1.8.0-amazon-corretto', type: 'jdk'
                    env.JAVA_HOME = "${jdk}"
                    env.PATH = "${jdk}/bin:${env.PATH}"
                    
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
