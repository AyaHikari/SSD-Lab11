flag = true

pipeline { 
    agent any 
    parameters {
        // These are types of parameters
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Select version')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests if true')
    }
    environment { 
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0'
    }
    stages { 
        stage('Build') { 
            steps { 
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}"
            } 
        } 
        stage('Test') { 
            when { 
                expression { 
                    params.executeTests // Conditional execution based on the boolean parameter
                } 
            }
            steps { 
                echo 'Testing Project' 
            } 
        } 
        stage('Deploy') { 
            steps { 
                echo 'Deploying Project' 
            } 
        } 
    } 
    post {
        always { 
            echo 'Post build condition running'
        }
        failure {
            echo 'Post Action if Build Failed'
        }
        success {
            echo 'Post Action if Build Succeeded'
        }
    }
}
