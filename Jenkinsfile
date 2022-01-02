pipeline {
   agent any

   triggers { pollSCM('* * * * *') }
   environment {
        TGTOKEN = credentials('tg-token')
        }
   stages {
      stage('sh') {
         steps {
            sh '/bin/true'
         }
      }  
   }
   post{
        always{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${PROJECT_NAME} Branch: ${BRANCH_NAME} Status:${BUILD_STATUS} 🚀\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}\nChange ID: ${CHANGE_ID} Title: ${CHANGE_TITLE}\nAuthor: ${CHANGE_AUTHOR}'"
         }
      }
   }