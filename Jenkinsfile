@Library('my-shared-lib') _
pipeline {
    agent any

    environment {
        APP_NAME = "jenkins-practice"
        VERSION = "1.0.0"
    }
    
    stages {
        stage('Pull Code'){
            steps{
               echo "Pulling code from ${APP_NAME}..." 
            }
        }
        stage('Build'){
            steps {
                echo "Building ${APP_NAME} version ${VERSION}..."
                bat 'dir'
            }
        }
        stage('test'){
            steps{
                echo "Testing ${APP_NAME}..."
            }
        }
        stage ('Deploy'){
            steps {
                echo "Deploying ${APP_NAME} version ${VERSION}..."
            }
        } 
    }
  post {
    success {
      echo "Pipeline for ${APP_NAME} completed successfully"
    }
    failure {
      echo "Pipeline for ${APP_NAME} failed"
    }
  }
}
