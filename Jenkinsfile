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
        TGTOKEN = credentials('tg-token')
        }
        always{
            sh 'curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text="${PROJECT_NAME}:${BUILD_STATUS} 🚀"'
         }
      }
   }