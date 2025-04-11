pipeline {
  agent any

  stages {
    stage(build) {
      steps {
        echo'Building the application...'
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
     echo 'Successfully ran'
    }
    failure {
      echo 'Job failed',
      mail to: '2024tm93167@wilp.bits-pilani.ac.in', subject: 'Build Failed', body: 'Job failed Check Jenkins logs.'
    }
}
}
