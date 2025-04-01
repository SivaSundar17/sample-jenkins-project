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
       echo'pipeline failed'
    }
  }
}
