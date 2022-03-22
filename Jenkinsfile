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
                    if (ENV_NAME == 'main') {
                        ENV_NAME = 'main'
                    } else if (ENV_NAME == 'dev' ) {
                        ENV_NAME = 'dev'    
                    }

                }

            }
        }

    }

}