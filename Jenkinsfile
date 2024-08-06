pipeline {
    agent any

    environment {
        // Define environment variables if needed
        IIS_SITE_PATH = "C:\\inetpub\\wwwroot"
    }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: '89df4684-1e78-400c-811e-c4d8c998e8a0', url: 'https://github.com/Siddarthan999/Jenkins-To-Do-List-App.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Include build steps if applicable
                echo 'Building the website...'
                // For example, if using npm for a React project:
                // bat 'npm install'
                // bat 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the website...'
                // Clean up the IIS site directory
                bat "del /Q /S ${env.IIS_SITE_PATH}\\*"

                // Copy new files to the IIS site directory
                bat "xcopy /E /Y /I build\\* ${env.IIS_SITE_PATH}\\"
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Deployment succeeded!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
