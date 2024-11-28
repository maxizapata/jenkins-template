pipeline {
    agent any

    environment {
        // Define environment variables if needed
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Pull the code from a Git repository
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies using npm
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests using npm or another testing tool
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                // Build the project if needed (e.g., bundling, transpiling)
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application
                // Example: Copy files to a server, push Docker image, etc.
                sh '''
                echo "Deploying application..."
                # Add deployment commands here
                '''
            }
        }
    }

    post {
        always {
            // Clean up the workspace after the build
            cleanWs()
        }

        success {
            // Actions to take when the pipeline succeeds
            echo 'Build succeeded!'
        }

        failure {
            // Actions to take when the pipeline fails
            echo 'Build failed!'
        }
    }
}