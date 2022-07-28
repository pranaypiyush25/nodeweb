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
        stage('install npm'){
            steps{
                echo 'started npm install'
                sh 'npm install'
            }
        }
        stage('version')
        {
            steps{
                sh 'docker --version'
            }
        }
        stage('Building image') {
      steps{
        sh 'docker build -t palakollu145/nodeweb .'
        }
      }
        stage('login&push')
        {
            steps{
                sh 'docker login -u palakollu145 -p Saikrish9949@'
                sh 'docker push palakollu145/nodeweb .'
            }
        }
        stage('pushing image') {
      steps{
         echo 'pushed'
        }
      }
    }
    
}
