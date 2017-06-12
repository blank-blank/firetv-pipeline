pipeline {
    agent any

    stages {
        stage('Prebuild Install') {
            steps {
                dir('.'){
                  deleteDir()
                }

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
            sh '/opt/android/sdk/bin/sdkmanager "platforms;android-22"'
            sh "git clone https://github.com/codepath/android-audio-video-demo.git application"
            sh "cp /opt/android/local.properties application/local.properties"
            sh "cd application; ./gradlew assemble" 
          }
        }
    }
}
