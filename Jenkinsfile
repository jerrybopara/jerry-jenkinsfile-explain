pipeline {
    agent any
    
    environment {
        NEW_VER = '10.1.2'
    }
    stages {
        stage("Main Branch - Build") {
            environment {
                STAGE_VER = '10.11.12'
            }
            when {
                branch 'main'
            }

            steps {
                echo "Building an application - only if the branch = main branch"
                echo "Running Build ID: ${env.BUILD_ID} on Branch: ${env.BRANCH_NAME} at Node: ${env.NODE_NAME}"
                echo "STAGE a New Version: ${env.STAGE_VER}"
            } 
        } 

        stage("Main Branch - Test") {
            when {
                branch 'main'
            }
            steps {
                echo 'Run this TEST stage - only if the branch = main branch'
                echo "New Version: ${env.NEW_VER}"
                echo "STAGE a New Version: ${env.STAGE_VER}"
            }
        }

        stage("Main Branch - Deploy") {
            when {
                branch 'main'
            }

            steps {
                echo 'Deploy the application - only if the branch = main branch'
            }
        }

// Dev Branch Stuff
        stage("Dev Branch - Build") {
            when {
                branch 'dev'
            }

            steps {
                echo 'Building an application - only if the branch = dev branch'                   
                echo "Running Build ID: ${env.BUILD_ID} on Branch: ${env.BRANCH_NAME} at Node: ${env.NODE_NAME}"
            } 
        } 

        stage("Dev Branch - Test") {
            when {
                branch 'dev'
            }
            steps {
                echo 'Run this TEST stage - only if the branch = dev branch'
            }
        }

        stage("Dev Branch - Deploy") {
            when {
                expression { env.BRANCH_NAME == 'dev' }
            }
            steps {
                echo 'Deploy the application - only if the branch = dev branch'
            }
        }

    } // end of stages
    post {
        always {
           echo 'I run always, No matter what the result is...'     
        }

        success {
            echo 'I only runs when i got Success...'

        }
        failure {
            echo 'I only runs when i got Failure...'

        }
    }
} // end of pipeline

