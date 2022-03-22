pipeline {
    agent any
    
    stages {
        stage("Main Branch - Build") {
            when {
                branch 'main'
            }

            steps {
                echo 'Building an application - only if the branch = main branch'                   
            } 
        } 

        stage("Main Branch - Test") {
            when {
                branch 'main'
            }
            steps {
                echo 'Run this TEST stage - only if the branch = main branch'
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
            // when {
            //     branch 'dev'
            // }

            when {
                env.Branch_Name == 'dev'
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

