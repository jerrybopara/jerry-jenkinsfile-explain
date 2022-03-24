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
            }
        }
    }


}