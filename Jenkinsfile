pipeline { 
    agent any 
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
    post {
        always { 
            // This action will always run, regardless of the build result
            echo 'Post build condition running'
        }

        failure {
            // This action will run only if the build fails
            echo 'Post Action if Build Failed'
        }

        success {
            // This action will run only if the build succeeds
            echo 'Post Action if Build Succeeded'
        }
    }
}
