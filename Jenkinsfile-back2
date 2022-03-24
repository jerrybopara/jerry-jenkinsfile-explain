pipeline {
    agent any

    environment {
        USER_NAME = "Jerry"
        USER_ID = "333"
    }

    stages {
        // stage("List env Variables") {
        //     steps {
        //         sh "printenv | sort"
        //     }
        // }

        stage("Using env Vars") {
            environment {
                USER_PATH = "/home/jerry"
                USER_ID = "222"
            }
            steps {
               echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"     
               sh 'echo BUILD_NUMBER = $BUILD_NUMBER'

               echo "Current User is ${env.USER_NAME}"
               echo "Current User ID is ${env.USER_ID} (type: ${env.USER_ID.class}" 
               echo "Current User Path ${env.USER_PATH}"

               script {
                   env.USERGROUP = 'Users'
                   env.USER_NAME = 'Cena'
                   env.TRIGGER_boolean = true
                   env.TRIGGER_when = "true"
               }
               sh 'echo User Group Inside the stage1 : $USERGROUP' 
               
               withEnv(["USER_PWD=secret", "IS_USER_ADMIN=false", "USER_PATH=/home/John", "USER_NAME=John", "USER_ID=111"]) {
                   echo "Current User Password is : ${env.USER_PWD}"
                   sh 'echo Current User is Admin? : $IS_USER_ADMIN'
                   echo "Current User is withENV:  ${env.USER_NAME} and USER_ID is: ${env.USER_ID}"
               }
               
               echo "Current User Name is: ${env.USER_NAME}" 
               echo "Current User ID is: ${env.USER_ID}"   

            }       
        }

        stage("Stage 2 - Checking TriggerBoolean.") {
            when {
                expression {
                    env.TRIGGER_boolean.toBoolean() == true
                }
            }
            steps{
                echo "Stage 2 Executed. : as TRIGGER_boolean is True."
            }

        }

        stage("Stage 3 - Checking TriggerWhen.") {
            environment {
                COUNT_FILES = sh(script: "ls -la /tmp | tail -n +4 | wc -l", returnStdout:true) 
            } 

            when {
                environment name: "TRIGGER_when", value: "true"
            }

            steps{
                echo "Stage 3 Executed. : as TRIGGER_when is True."
                echo "There are ${env.COUNT_FILES} files in /tmp Folder." 
            }

        }

    }
}