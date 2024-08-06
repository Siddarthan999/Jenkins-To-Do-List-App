pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Siddarthan999/Jenkins-To-Do-List-App.git'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Define path to the local server
                    def websitePath = 'C:\\inetpub\\wwwroot\\index.html'

                    // Copy the single file to IIS directory
                    bat "copy /Y index.html ${websitePath}"
                }
            }
        }
    }
}
