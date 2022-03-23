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
            }
            steps {
               echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"     
               sh 'echo BUILD_NUMBER = $BUILD_NUMBER'

               echo "Current User is ${env.USER_NAME}"
               echo "Current User ID is ${env.USER_ID} (type: ${env.USER_ID.class}" 
               echo "Current User Path ${env.USER_PATH}"
               
            }
        }    




    }
}