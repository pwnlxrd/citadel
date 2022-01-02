pipeline {
   agent any

   triggers { pollSCM('* * * * *') }

   stages {
      stage('sh') {
         steps {
            sh '/bin/true'
         }
      }  
   }
   post{
    environment {
        TG-TOKEN = credentials('tg-token')
        }
        always{
            sh 'curl -s -X POST https://api.telegram.org/bot$TG-TOKEN/sendMessage -d chat_id=-456374469 -d text="${PROJECT_NAME}:${BUILD_STATUS} 🚀"'
         }
      }
   }