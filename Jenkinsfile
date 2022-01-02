pipeline {
    agent any

    stages {
        stage('Do nothing') {
            steps {
                sh '/bin/true'
            }
        }
    }
    post{
        always{
            telegramSend(message:'${PROJECT_NAME}:${BUILD_STATUS}',chatId:-456374469)
         }
     }
}
