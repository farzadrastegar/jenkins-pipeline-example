throttle(['throttleDocker']) {
  node('docker') {
    wrap([$class: 'AnsiColorBuildWrapper']) {
      try{
        stage('Setup') {
          checkout scm
          sh '''
            echo "Setup passed!"
          '''
        }
        stage('Test'){
          parallel (
            "unit": {
              sh '''
                echo "Unit test passed!"
              '''
            },
            "functional": {
              sh '''
                echo "Functional test passed!"
              '''
            }
          )
        }
        stage('Capacity Test') {
          sh '''
            echo "Capacity test passed!"
          '''
        }
      }
      finally {
        stage('Cleanup') {
          sh '''
            echo "Cleaning up..."
            echo "All done!"
          '''
        }
      }
    }
  }
}

