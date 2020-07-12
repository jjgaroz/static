pipeline {
     agent any
     stages {
         stage ('Upload to AWS.') {
              steps {
                retry(3) {
                    withAWS(region:'eu-ireland', credentials: 'aws-static') {
                        s3Upload(file:'index.html', bucket:'jenkinsjjgaroz', path:'index.html')
                    }
                }
            }
        }
    }
