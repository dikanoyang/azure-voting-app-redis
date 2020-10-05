pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
       stage ("Build Docker") {
            steps {
                sh(script: 'docker images -a')
                sh(script: '''
                cd azure-vote/
                docker images -a
                docker build -t jenkins-pipline .
                docker images -a
                cd ../
                '''
                )
            }
       }
   }
}
