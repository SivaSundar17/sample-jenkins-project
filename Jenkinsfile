pipeline {
  agent any

  stages {
    stage(build) {
      steps {
        echo'Building the application...'
      }
    }
    stage('Compile Java') {
      steps {
      // Compile Java file (adjust according to your project structure)
        sh 'javac MyJavaFile.java' // Compiling your Java file
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
      mail to: 'team@example.com', subject: 'Build Failed', body: 'Check Jenkins logs.'
    }
}
}
