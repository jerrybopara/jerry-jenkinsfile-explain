pipeline {
    agent any

    environment {
        USER_NAME = "Jerry"
        USER_ID = "333"
    }

    stages{
        stage("Print Global ENV's") {
            steps {
                echo "USER_NAME is: ${USER_NAME}"
            }
        }
    }


}