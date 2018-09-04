throttle(['throttleDocker']) {
  node('docker') {
    wrap([$class: 'AnsiColorBuildWrapper']) {
      try{
        stage('Setup') {
          checkout scm
          sh '''
            echo "======1======Setup passed!"
          '''
        }
        stage('Test'){
          parallel (
            "unit": {
              sh '''
                echo "======2=======Test unit passed!"
              '''
            },
            "functional": {
              sh '''
                echo "======3========Test functional passed!"
              '''
            }
          )
        }
        stage('Capacity Test') {
          sh '''
            echo "=============4========Capacity test passed!"
          '''
        }
      }
      finally {
        stage('Cleanup') {
          sh '''
            echo "===========END============All done!"
          '''
        }
      }
    }
  }
}

