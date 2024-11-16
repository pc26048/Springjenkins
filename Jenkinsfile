pipeline {
    agent any

    tools{
 	jdk 'JDK17'
 	maven 'MAVEN3'
 	}

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from Git repository...'
                checkout scm
            }
        }

        stage('Maven Compile') {
            steps {
                echo 'Compiling the project...'
                bat 'mvn clean compile'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Running unit tests...'
                bat 'mvn test'
            }
        }

        stage('Code Coverage') {
            steps {
                echo 'Generating Jacoco coverage report...'
                
            }
        }

        stage('Build Package') {
            steps {
                echo 'Packaging the application...'
                bat 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add Windows-specific deployment commands, e.g., copying files or running scripts
                // Example: bat 'copy target\\*.jar C:\\deploy\\folder\\'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
        always {
            echo 'Cleaning up workspace...'
            cleanWs()
        }
    }
}


