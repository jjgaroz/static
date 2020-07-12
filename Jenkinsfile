pipeline {
     agent any
     stages {
          stage('Lint HTML') {
            steps {
                sh 'echo Linting HTML'
                sh 'tidy -q -e *.html'
            }
        }
         stage ('Upload to AWS.') {
              steps {
                retry(3) {
                    withAWS(region:'eu-west-1', credentials: 'aws-static') {
                        s3Upload(file:'index.html', bucket:'jenkinsjjgaroz', path:'index.html')
                    }
                }
            }
         }
        }
    }
