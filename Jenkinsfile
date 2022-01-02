pipeline {
   agent any

   triggers { pollSCM('* * * * *') }
//    environment {
//         TGTOKEN = credentials('tg-token')
//         }
   stages {
      stage('sh') {
         steps {
            sh '/bin/true'
         }
      }  
   }
   post{
        always{
            withCredentials([string(credentialsId: 'tg-token', variable: 'TGTOKEN')]) {
            sh 'curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text="${PROJECT_NAME}:${BUILD_STATUS} 🚀"'
            }
         }
      }
   }