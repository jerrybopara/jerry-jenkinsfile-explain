pipeline {
    agent any
    
    stages {
        stage("Build") {
            
            steps {
                echo 'building an application...'                   
            } 
        } 

        stage("Test Main Branch") {
            when {
                branch 'main'
            }
            steps {
                echo 'run this stage - ony if the branch = main branch'
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

