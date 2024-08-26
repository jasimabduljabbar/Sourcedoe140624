pipeline {
    agent any

    tools {
        // Install the JDK from the tools configuration
        jdk 'JDK11'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                git 'https://github.com/your-repo-url.git'
            }
        }
        
        stage('Build') {
            steps {
                // Compile the Java source code
                sh 'javac HelloWorld.java'
            }
        }
        
        stage('Test') {
            steps {
                // Normally, we would run tests here. For simplicity, we will skip actual tests.
                echo 'Skipping tests...'
            }
        }
        
        stage('Package') {
            steps {
                // Package the application (in this case, just a jar file)
                sh 'jar cvf HelloWorld.jar HelloWorld.class'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application
                // This could be copying the jar to a server, but here we'll just echo a message.
                echo 'Deploying HelloWorld.jar...'
            }
        }
    }
    
    post {
        always {
            // Archive the artifacts or perform any cleanup txt
            archiveArtifacts artifacts: '**/*.class, **/*.jar', allowEmptyArchive: true
        }
    }
}
