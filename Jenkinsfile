pipeline {
    agent any

    stages {
        stage('Prebuild Install') {
            steps {
                dir('.'){
                  deleteDir()
                }
                sh "wget https://dl.google.com/android/repository/platform-tools-latest-linux.zip"
                sh "unzip platform-tools-latest-linux.zip"
                sh "ls"
                echo "Running ${env.BUILD_ID}"
            }
        }
        stage('Connect to FireTV') {
            steps {
                sh "adb kill-server"
                sh "adb start-server"
                sh "adb connect 192.168.1.75"
                sh "adb devices"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'

            }
        }
    }
}
