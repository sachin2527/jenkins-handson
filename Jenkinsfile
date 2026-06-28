pipeline {
    agent any
    
    stages {
        stage('Pull Code'){
            steps{
                git branch: 'main',
                url: 'https://github.com/sachin2527/jenkins-handson'
            }
        }
        stage('Build'){
            steps {
                echo 'Building the application...'
                bat 'dir'
            }
        }
        stage('test'){
            steps{
                echo 'deploying application...'
            }
        }
        stage ('Notification'){
            steps {
                echo 'Sending notification to Team!'
            }
        } 
    }
  post {
    success {
      echo 'Pipeline completed successfully' 
    }
    failure {
      echo 'Pipeline failed'
    }
  }
}
