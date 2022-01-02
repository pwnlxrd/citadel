pipeline {
   agent any

   triggers { pollSCM('* * * * *') }
   environment {
        TGTOKEN = credentials('tg-token')
        GITHUB_PROJECT = "pwnlxrd/citadel"
        }
   stages {
      stage('mirroring') {
         steps {
            sh 'git push --mirror git@github.com:$GITHUB_PROJECT.git'
         }
      }  
   }
   post{
        success{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME}\nBranch: ${BRANCH_NAME}\nStatus: 🚀 success 🚀\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}'"
         }
        fixed{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME}\nBranch: ${BRANCH_NAME}\nStatus: 🔧 fixed 🔧\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}'"
         }
        failure{
            sh "curl -s -X POST https://api.telegram.org/bot$TGTOKEN/sendMessage -d chat_id=-456374469 -d text='Project: ${JOB_NAME}\nBranch: ${BRANCH_NAME}\nStatus: ❗️❗️❗️ failure ❗️❗️❗️\nBuild ID:${BUILD_ID} Build Number: ${BUILD_NUMBER}'"
         }
      }
   }