pipeline {
  agent any
    parameters {
      choice(name: 'ENV', choices: ['Staging', 'Production'], description: 'Choose deployment environment')
  }
  stages {
    stage(build) {
      steps {
        echo'Building the application...'
      }
    }
    stage('Checkout') {
      steps {
        // Checkout code from repository
        git branch: 'feature/add-comment', url: 'https://github.com/SivaSundar17/sample-jenkins-project.git'
          }
      }
    stage('Compile Java') {
      steps {
      // Compile Java file (adjust according to your project structure)
        bat 'javac HelloWorld.java' // Compiling your Java file
      }
    }

    stage(test) {
      steps {
        echo 'Testing the application...'
      }
    }
    
    stage(deploy) {
      steps {
        script {
          if (params.ENV == 'Staging') {
            echo "Deploying to Staging environment..."
            // Example: simulate dev deploy

          } else if (params.ENV == 'Production') {
            echo "Deploying to Staging environment..."
            // Example: simulate Production deploy
    
          }  else {
            error "Invalid environment selected!"
          }
      }
    }
  }
  }
  post {
    success {
     echo 'Successfully ran'
    }
    failure {
      script {
        if (params.ENV == 'Staging') {
        echo 'Job failed'
       mail to: '2024tm93167@wilp.bits-pilani.ac.in', subject: 'Build Failed during deployment to Staging', body: 'Build Failed while deploying to Staging. Check Jenkins logs for more information.'
      }
      if (params.ENV == 'Staging') {
        echo 'Job failed'
       mail to: '2024tm93167@wilp.bits-pilani.ac.in', subject: 'Build Failed during deployment to Staging', body: 'Build Failed while deploying to Staging. Check Jenkins logs for more information.'
      }
    }
}
}
}
