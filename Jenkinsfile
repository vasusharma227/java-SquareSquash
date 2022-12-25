pipeline {
  agent any
  stages {
    stage('Log version') {
      parallel {
        stage('Log version') {
          steps {
            sh '''mvn --version
git --version
java -version'''
          }
        }

        stage('search POM file') {
          steps {
            fileExists 'pom.yml'
          }
        }

      }
    }

    stage('compile') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('status') {
      steps {
        writeFile(file: 'status.txt', text: 'hey its working!')
      }
    }

  }
}