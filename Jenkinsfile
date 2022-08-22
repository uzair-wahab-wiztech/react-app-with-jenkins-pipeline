pipeline {
    agent {
         docker { 
            image 'node:16-alpine' 
            args '-p 3000:3000'
        }
    }
    
    environment {
        SURGE_TOKEN = ''
    }
    
    stages {
        stage('Build') {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        .stage("Deploy") {
            steps {
                sh "npm install -g surge"
                sh "surge build uzair-jenkins-pipeline.surge.sh ${SURGE_TOKEN}"
            }
        }
    }
}