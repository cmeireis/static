pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Lint HTML') {
          steps {
            sh 'tidy -q -e *.html'
          }
        }
        stage('Build') {
          steps {
            withAWS(credentials: 'aws-static') {
              s3Upload(file: 'index.html', bucket: 'cmstatic-jenkins')
            }

          }
        }


      }
    }

  }
}
