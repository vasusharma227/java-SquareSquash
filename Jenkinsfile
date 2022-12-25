pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        node(label: 'testing') {
          sh 'echo "testing build branch"'
        }

      }
    }

    stage('maintain') {
      steps {
        sh 'echo "maintain testing"'
      }
    }

    stage('compile') {
      steps {
        sh 'echo "hello"'
      }
    }

    stage('analyse') {
      steps {
        build(job: 'java-SquareSquash', quietPeriod: 2)
      }
    }

    stage('done') {
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