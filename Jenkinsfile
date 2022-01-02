pipeline {
   agent any

   triggers { pollSCM('* * * * *') }
   environment {
        TGTOKEN = credentials('tg-token')
        PROJECT_
        }
   stages {
      stage('sh') {
         steps {
            echo 'test - ${PROJECT_NAME}:${BUILD_STATUS} ${BUILD_ID} ${BUILD_NUMBER}'
            sh '/bin/true'
         }
      }  
   }
   post{
        always{
            sh 'curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text="${PROJECT_NAME}:${BUILD_STATUS} 🚀"'
         }
      }
   }