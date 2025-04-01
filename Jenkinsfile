pipeline {
  agent any

  stages {
    stage(build) {
      steps {
        echo'Building the application...'
        slackSend channel: '#builds', color: 'good', message: "${env.JOB_NAME} - #${env.BUILD_NUMBER} Started by changes from ${env.GIT_NAME}(<${env.BUILD_URL}|Open>)", teamDomain: 'teamnamehere', tokenCredentialId: 'tokenidhere'
      }
    }

    stage(test) {
      steps {
        echo 'Testing the application...'
      }
    }
    
    stage(deploy) {
      steps {
        echo 'Deploying the application...'
      }
    }
  }

  post {
    success {
     message:'Successfully ran'
    }

    failure {
       message:'pipeline failed'
    }
  }
}
