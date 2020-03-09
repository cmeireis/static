pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh '''\'\'\'
echo "Hello world with AWS Creds" /
tidy -q -e *.html
\'\'\''''
      }
    }

    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static') {
          s3Upload(bucket: 'cmstatic-jenkins', file: 'index.html')
        }

      }
    }

  }
}