pipeline {
  agent any

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
        echo 'Deploying the application...'
      }
    }
  }

  post {
    success {
     echo 'Successfully ran'
    }
    failure {
      echo 'Job failed'
     // mail to: 'team@example.com', subject: 'Build Failed', body: 'Check Jenkins logs.'
    }
}
}
