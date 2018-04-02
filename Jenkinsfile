pipeline {
  agent {
    docker {
      image 'node::6-alpine'
      args '-p 3000:3000'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        build(job: 'Build', propagate: true, quietPeriod: 1, wait: true)
        sh 'npm install'
      }
    }
  }
}