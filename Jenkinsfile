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
            }
        }
        stage('Connect to FireTV') {
            steps {
                sh "platform-tools/adb kill-server"
                sh "platform-tools/adb start-server"
                sh "platform-tools/adb connect 192.168.1.75"
                sh "platform-tools/adb devices"
            }
        }
        stage('Clone application source code'){
          steps {
            sh "git clone https://github.com/codepath/android-audio-video-demo.git application"
            sh "cd application;./gradlew clean assemble"  
          }
        }
        stage('Deploy') {

            def apk_file = "application/application.apk"

            steps {
                echo 'Deploying....'
                sh "adb install ${apk_file}"

            }
        }
    }
}
