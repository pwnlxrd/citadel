pipeline {
   agent any

   stages {
      stage('sh') {
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
}