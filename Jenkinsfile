pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      steps {
        node(label: 'testing') {
          sh 'echo "testing build branch"'
        }

      }
    }

    stage('maintain') {
      agent any
      steps {
        sh 'echo "maintain testing"'
      }
    }

    stage('compile') {
      agent any
      steps {
        sh 'echo "hello"'
      }
    }

    stage('analyse') {
      agent any
      steps {
        build(job: 'java-SquareSquash', quietPeriod: 2)
      }
    }

    stage('done') {
      agent any
      steps {
        node(label: 'testing') {
          sh 'echo "heloo done"'
        }

      }
    }

  }
  environment {
    var = '2'
    char = '4'
  }
}