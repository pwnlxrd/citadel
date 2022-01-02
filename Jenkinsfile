pipeline {
   agent any

   triggers { pollSCM('* * * * *') }
   environment {
        TGTOKEN = credentials('tg-token')
        }
   stages {
      stage('sh') {
         steps {
            echo "The build number is ${env.BUILD_NUMBER}"
            echo 'test - ${PROJECT_NAME}:${env.BUILD_STATUS} ${BUILD_ID} ${env.BUILD_NUMBER}'
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