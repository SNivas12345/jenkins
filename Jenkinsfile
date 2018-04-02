pipeline {
  agent {
    node {
      label 'Build'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        build(job: 'Build', propagate: true, quietPeriod: 1, wait: true)
      }
    }
  }
  environment {
    jenkins = '1'
  }
}