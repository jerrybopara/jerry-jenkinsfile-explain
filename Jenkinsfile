pipeline {
    agent { label 'jerryme106' }

    environment {
        USER_NAME = "Jerry"
        USER_ID = "333"
    }

    stages{
        stage('Check Hostname') {
            environment {
                MyHostName = sh(script: "hostname", returnStdout:true)
            }    

            steps{
                echo "MyHostName is: ${env.MyHostName}."
                sh 'docker ps -a'
            }
        }

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
                    env.TriggerBool = true 
                    env.TriggerWhen = "true" 
                }    

                withEnv(["USER_NAME=Jerry Bopara", "USER_ID=555", "USER_AGE=32"]) {
                         echo "My UserName is : ${env.USER_NAME} and USER_ID is : ${env.USER_ID} and USER_AGE is : $USER_AGE"
                         sh 'echo My UserName is : $USER_NAME and USER_ID is : $USER_ID'
                }

                sh 'echo My UserName is : $USER_NAME and USER_ID is : $USER_ID'
            }

        }
        stage('Sanity Checks') {
            steps {
                input "Do you want to test Boolean & env as boolean ?"
            }
        }

        stage("Stage 2: Execute when Bool is ture") {
            when {
                expression {
                    env.TriggerBool.toBoolean() == true
                }
            }
            steps {
                echo "Stage2 - TriggerBool is True."
            }    
        }

        stage("Stage 3: Executes only when TriggerWhen is True.") {
            when {
                environment name: "TriggerWhen", value: "true"
            }

            steps {
                 echo "Stage3 - TriggerWhen is True."
            }

        }



    }


}