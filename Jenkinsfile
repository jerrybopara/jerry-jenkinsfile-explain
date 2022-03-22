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

                script {
                    if (ENVIRONMENT_NAME == 'main') {
                        ENV_NAME = 'main'
                    } else if (ENVIRONMENT_NAME == 'dev' ) {
                        ENV_NAME = 'dev'    
                    }

                }

                echo 'Building Branch: ' + env.BRANCH_NAME
                echo 'Build Number: ' + env.BUILD_NUMBER
                echo 'Building Environment: ' + ENV_NAME

                echo "Running your service with environemnt ${ENV_NAME} now"
            }
        }

    }

}