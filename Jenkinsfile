@Library('my-shared-lib') _
pipeline {
    agent any

    parameters{
        string(
            name: 'APP_NAME',
            defaultValue: 'jenkins-practice',
            description: 'Enter application name'
        )
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'staging', 'prod'],
            description: 'Select deployment environment'
        )
    booleanParam(
        name: 'RUN_TESTS',
        defaultValue: true,
        description: 'Run tests ?'
    )}
    stages {
        stage('Pull Code'){
            steps{
               echo "Pulling code from ${params.APP_NAME}..." 
            }
        }
        stage('Build'){
            steps {
                buildApp ("${params.APP_NAME}")
            
            }
        }
        stage('test'){
            when {
            expression {params.RUN_TESTS == true} }
            steps{
                testApp ("${params.APP_NAME}")
            }
        }
        stage ('Deploy'){
            steps {
                echo "Deploying ${params.APP_NAME} version ${params.ENVIRONMENT}..."
                echo "webhooKKK"
            }
        } 
    }
  post {
    success {
      echo "Pipeline for ${params.APP_NAME} completed successfully"
    }
    failure {
      echo "Pipeline for ${params.APP_NAME} failed"
    }
  }
}
