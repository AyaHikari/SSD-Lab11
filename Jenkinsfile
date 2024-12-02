flag = true

pipeline { 
    agent any 
    tools {
        maven 'Maven' // Added Maven tool configuration
    }
    environment { 
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0' // Added new environment variable
    }
    stages { 
        stage('Build') { 
            steps { 
                echo 'Building Project'
                // Using environment variable
                // To output the value of variable in string, use " "
                echo "Building version ${NEW_VERSION}"
                
                // Use nvm-windows to install a specific Node.js version
                bat 'nvm install 16.15.0' // Replace with the desired Node.js version
                bat 'nvm use 16.15.0' // Use the specified version
            } 
        } 
        stage('Test') { 
            when { 
                expression { 
                    flag == true // Ensuring the flag variable logic remains
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
