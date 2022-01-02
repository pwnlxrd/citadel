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
            sh 'curl -s -X POST https://api.telegram.org/bot$tg-token/sendMessage -d chat_id=-456374469 -d text="${PROJECT_NAME}:${BUILD_STATUS} 🚀"'
         }
      }
   }