pipeline {
    agent any
    
    environment {
        ENV_NAME = "${env.BRANCH_NAME}"
    }

    // --------------- 
    stages { 
        stage('Build') {
            steps {
                // echo "Running Build ID: ${env.BUILD_ID} on Branch: ${env.BRANCH_NAME} at Node: ${env.NODE_NAME}"
                echo "Build Process Started../"
                echo "Running Build ID: ${env.BUILD_ID} - on Branch: ${env.BRANCH_NAME} - at Node: ${env.NODE_NAME}"
              
            }
        }

        stage('Test') {
            steps {
                echo "TEST Process Started../"
                echo "Testing Build ID: ${env.BUILD_ID} - on Branch: ${env.BRANCH_NAME} - at Node: ${env.NODE_NAME}"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deployment Process Started../"
                echo "Deployment Build ID: ${env.BUILD_ID} - on Branch: ${env.BRANCH_NAME} - at Node: ${env.NODE_NAME}"
            }
        }        
    }

}