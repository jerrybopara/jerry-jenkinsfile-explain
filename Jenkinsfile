pipeline {
    agent any

    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'Just a False Description.')
    }
    
    stages {
        stage('Setup Parameters') {
            steps {
                script {
                    properties([
                        parameters([
                            choice(
                                choices: ['ONE', 'TWO', 'THREE'],
                                name: 'MyChoice_01'

                            ),

                            booleanParam(
                                defaultValue: true,
                                description: 'CheckBox Params',
                                name: 'MyBoolean_01'
                            ),

                            text(
                                defaultValue: '''
                                this is multi-line 
                                string parameter 
                                example.''',
                                name: 'MyMultiline_01'

                            ),
                            
                            string(
                                defaultValue: 'hello',
                                name: 'MyString_01',
                                trim: true 
                            )
                        ])
                    ])
                }
            }    
        }

        stage('Print the Parameters.') {
            steps {
                echo 'Hi parameters'
                echo "It's my Choice Parameter: ${params.MyChoice_01}"
                echo "It's my Boolean Parameter: ${params.MyBoolean_01}"
                echo "It's my TEXT Parameter: ${params.MyMultiline_01}"
                echo "It's my STRING Parameter: ${params.MyString_01}"
                
            }

        }



        stage("Main Branch - Build") {
            when {
                branch 'main'
            }   

            steps {
                echo "Building an application - only if the branch = main branch"
                echo "Running Build ID: ${env.BUILD_ID} on Branch: ${env.BRANCH_NAME} at Node: ${env.NODE_NAME}"
                echo "${params.Greeting} World!"
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

