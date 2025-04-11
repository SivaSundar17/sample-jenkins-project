pipeline {
  agent any
    parameters {
      choice(name: 'Staging', choices: ['Staging', 'Production'], description: 'Choose deployment environment')
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
      echo 'Job failed'
     mail to: 'shivalalitha17@gmail.com', subject: 'Build Failed', body: 'Check Jenkins logs.'
    }
}
}
