pipeline {
  agent any
  stages {
        stage('Test Git') {
            steps {
                bat 'git --version' 
            }
        }
    }
  
  stages {
        stage('Build') {
            steps {
                echo 'Building..'
              // Here you can define commands for your build
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                // Here you can define commands for your tests
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Here you can define commands for your deployment
            }
        }

  }
}

