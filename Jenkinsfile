pipeline {
    agent any

    stages {
        stage('Prebuild Install') {
            steps {
                dir('.'){
                  deleteDir()
                }
                //sh "wget https://dl.google.com/android/repository/platform-tools-latest-linux.zip"
                //sh "wget https://dl.google.com/android/repository/sdk-tools-linux-3859397.zip"
                //sh "unzip sdk-tools-linux-3859397.zip"
                //sh './tools/bin/sdkmanager "platforms;android-25"'
                //sh "unzip platform-tools-latest-linux.zip"
                //sh './tools/bin/sdkmanager --list'
            }
        }
        stage('Connect to FireTV') {
            steps {
                //sh "platform-tools/adb kill-server"
                //sh "platform-tools/adb start-server"
                //sh "platform-tools/adb connect 192.168.1.75"
                //sh "platform-tools/adb devices"
                echo "placeholder for connection step"
            }
        }
        stage('Clone application source code'){
          steps {
            sh "git clone https://github.com/codepath/android-audio-video-demo.git application"
            sh "cp /opt/android/local.properties application/local.properties"
            sh "cd application; ./gradlew assemble" 
          }
        }
    }
}
