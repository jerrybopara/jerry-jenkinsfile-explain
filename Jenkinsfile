pipeline {
    agent any
    
    stages {
        stage("Build") {
            
            steps {
                echo 'building an application...'                   
            } 
        } 

        stage("Test") {
            when {
                experssion {
                    BRANCH_NAME == 'main'
                }
            }
            
            steps {
                echo 'testing the application...'
                echo 'Only when am in MAIN Branch...'
            }
        }

        stage("Deploy") {

            steps {
                echo 'Deploying the application...'
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

