pipeline {
    agent any

    environment {
        // Define the JDK installation name based on your Jenkins configuration
        JDK_INSTALLATION = 'Java 8'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                checkout scm
            }
        }

        stage('Set up JDK') {
            steps {
                // Define the JDK version and tool name
                def jdkVersion = '8'
                def jdkTool = tool name: "${JDK_INSTALLATION}", type: 'JDK'
                
                // Set JAVA_HOME to the selected JDK
                withEnv(['JAVA_HOME=' + "${jdkTool}", "PATH+JDK=${jdkTool}/bin"]) {
                    // Print JAVA_HOME for verification
                    sh 'echo $JAVA_HOME'
                }
            }
        }

        stage('Build and Analyze') {
            steps {
                // Run the Maven build with SonarQube analysis
                sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=wizebird -Dsonar.organization=wizebird -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=752c540a36bc5c7763eae3e764f380acc80dde4a'
            }
        }
    }

    post {
        always {
            // Clean up workspace (optional)
            cleanWs()
        }
    }
}
