pipeline { 
    agent any 
    environment { 
        flag = 'false' // Define the variable here
    }
    stages { 
        stage('Build') { 
            steps { 
                echo 'Building..' 
                // Commands for your build 
            } 
        } 
        stage('Test') { 
            when { 
                expression { 
                    env.flag == 'false' // Access the variable from the environment
                } 
            }
            steps { 
                echo 'Testing..' 
                // Commands for your tests 
            } 
        } 
        stage('Deploy') { 
            steps { 
                echo 'Deploying....' 
                // Commands for your deployment 
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
