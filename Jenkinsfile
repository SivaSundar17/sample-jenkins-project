pipeline {
  agent any
    parameters {
    choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Select environment to deploy')
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
          if (params.ENV == 'dev') {
            echo "Deploying to Development environment..."
            // Example: simulate dev deploy
            bat 'echo Deploying to DEV'
          } else if (params.ENV == 'staging') {
            echo "Deploying to Staging environment..."
            // Example: simulate staging deploy
            bat 'echo Deploying to STAGING'
          } else if (params.ENV == 'prod') {
            echo "Deploying to Production environment..."
            // Example: simulate prod deploy
            bat 'echo Deploying to PRODUCTION'
          } else {
            error "Invalid environment selected!"
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
