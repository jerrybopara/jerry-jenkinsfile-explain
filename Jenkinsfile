pipeline {
    agent any

    environment {
        USER_NAME = "Jerry"
        USER_ID = "333"
    }

    stages{
        stage("Print Global ENV's") {
            environment {
                USER_AGE = "31"
                USER_ID = "222"
            }
            steps {
                echo "USER_NAME is: ${USER_NAME}"
                echo "USER_NAME is: ${env.USER_NAME}"
                sh 'echo USER_ID : $USER_ID'
                echo "USER AGE is : ${USER_AGE}"       
                echo "Current User ID is ${env.USER_ID} (type: ${env.USER_ID.class}" 
                
                script {
                    env.USER_NAME = 'Bopara'
                    env.USER_ID = '111'
                }    

                sh 'echo My UserName is : $USER_NAME and USER_ID is : $USER_ID'

                withEnv(["USER_NAME=Jerry Bopara", "USER_ID=555", "USER_AGE=32"]) {
                         echo "My UserName is : ${env.USER_NAME} and USER_ID is : ${env.USER_ID} and USER_AGE is : $USER_AGE"
                         sh 'echo My UserName is : $USER_NAME and USER_ID is : $USER_ID'
                }
            }

        }
    }


}