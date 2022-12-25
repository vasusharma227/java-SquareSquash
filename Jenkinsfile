pipeline {
  agent any
  stages {
    stage('Log tool version') {
      parallel {
        stage('Log tool version') {
          agent any
          steps {
            node(label: 'testing') {
              sh '''mvn --version
git --version
java -version
'''
            }

          }
        }

        stage('Check for POM') {
          steps {
            fileExists 'POM.xml'
          }
        }

      }
    }

    stage('Build with maven') {
      agent any
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('post build steps') {
      agent any
      steps {
        writeFile(file: 'status.txt', text: 'hey it worked!')
      }
    }

  }
  environment {
    var = '2'
    char = '4'
  }
}