pipeline {
    agent any
    
    environment {
        SURGE_TOKEN = 'b5ddb0f207922e6adb34f67a69b720ad'
    }
    
    stages {
        stage('Build') {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "npm install -g surge"
                sh "surge build uzair-jenkins-pipeline.surge.sh ${SURGE_TOKEN}"
            }
        }
    }
}