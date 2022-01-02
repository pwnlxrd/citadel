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
        success{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME} Branch: ${BRANCH_NAME} Status: success 🚀\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}\nChange ID: ${CHANGE_ID} Title: ${CHANGE_TITLE}\nAuthor: ${CHANGE_AUTHOR}'"
         }
        fixed{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME} Branch: ${BRANCH_NAME} Status: fixed 🔧\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}\nChange ID: ${CHANGE_ID} Title: ${CHANGE_TITLE}\nAuthor: ${CHANGE_AUTHOR}'"
         }
        failure{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME} Branch: ${BRANCH_NAME} Status: failure ❗️❗️❗️\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}\nChange ID: ${CHANGE_ID} Title: ${CHANGE_TITLE}\nAuthor: ${CHANGE_AUTHOR}'"
         }
      }
   }