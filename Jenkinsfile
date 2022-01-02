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
            telegramSend(message:'test',chatId:-456374469)
         }
      }
   }