pipeline {
    agent any

    stages {
        // stage("List env Variables") {
        //     steps {
        //         sh "printenv | sort"
        //     }
        // }

        stage("Using env Vars") {
            steps {
               echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"     
               sh 'echo BUILD_NUMBER = $BUILD_NUMBER'

            }
        }    




    }
}