pipeline {
    agent any
    tools {
    nodejs 'nodejs'
    dockerTool 'docker'
}
    stages {
        stage('git') {
            steps {
                echo 'pulling code'
                git branch: 'main', url: 'https://github.com/palakollu145/nodeweb'
            }
        }
        stage('Bug Cap')
        {
            steps{
                echo 'bug cap'
            }
        }
        stage('Build'){
            steps{
                echo 'started npm install'
                sh 'npm install'
            }
        }
        stage('Unit Test')
        {
            steps{
                echo 'Unit Test'
            }
        }
        stage('Code Coverage')
        {
            steps{
                echo 'Code Coverage'
            }
        }
        stage('Static Code Analysis TPL Scan')
        {
            steps{
                echo 'Static Code Analysis TPL Scan'
            }
        }
        stage('Docker Build') {
      steps{
        sh 'docker build -t palakollu145/nodeweb .'
        }
       }
        stage('Container Vulnerability Scan')
        {
            steps{
                echo 'Container Vulnerability Scan'
            }
        }
        stage('Docker Publish to stable Repo')
        {
            steps{
                sh 'docker login -u palakollu145 -p Saikrish9949@'
                sh 'docker push palakollu145/nodeweb'
                
                
                
            }
        }
        stage('removing unused images')
        {
            steps{
                sh 'docker container prune --force'
                sh 'docker image prune --all --force'
                sh 'docker ps'
                sh 'docker images'
            }
        }
        stage('Deploy to QA cluster')
        {
            steps{
                echo 'Deploy to QA cluster'
            }
        }
        stage('Test')
        {
            steps{
                echo 'Test'
            }
        }
    
}
}
