pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven to autoamtically build and manage'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                echo 'Running integration tests...'
                echo 'Junit can be unsed for unit testing and Selenium can be used for integration testing'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis'
                echo 'sonarQube can be used'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan on the code'
                echo 'Tool recommended: OWASP ZAP'

            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server (e.g., AWS EC2 instance)...'
                echo 'Deployment tool: jenkins server'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                echo 'tool: Apache JMeter'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server (e.g., AWS EC2 instance)...'
                echo 'tool: Jenkins pipeline with AWS Codedeploy plugin'

            }
        }
    }
    post {
        success {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Successful",
                      body: 'The build was successful. Congratulations!',
                      to: 'bhawnasharma5779@gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Failed",
                      body: 'The build has failed. Please make the necessary changes and debug ',
                      to: 'bhawnasharma5779@gmail.com',
                      attachLog: true
        }
    }
}
