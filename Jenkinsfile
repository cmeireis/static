pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        withAWS(credentials:'aws-static') {
    s3Upload(file:'index.html', bucket:'cmstatic-jenkins', path:'*/')
          
}
      }
    }

  }
}
