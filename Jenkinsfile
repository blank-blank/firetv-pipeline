pipeline {
    agent any

    stages {
        stage('Prebuild Install') {
            steps {
                deletedir
                sh "wget https://dl.google.com/android/repository/sdk-tools-darwin-3859397.zip"
                sh "unzip sdk-tools-darwin-3859397.zip"
                sh "ls"
                echo "Running ${env.BUILD_ID}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'

                echo "adb kill-server"
                echo "adb start-server"
                echo "db connect 192.168.1.75"
            }
        }
    }
}
