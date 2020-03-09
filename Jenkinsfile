pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            withAWS(credentials: 'aws-static') {
              s3Upload(file: 'index.html', bucket: 'cmstatic-jenkins')
            }

          }
        }

        stage('Lint HTML') {
          steps {
            sh 'tidy -q -e *.html'
          }
        }

      }
    }

  }
}