pipeline {
     agent any
     stages {
         stage('Lint HTML') {
              steps {
                  sh 'echo "Hello World with AWS upload!"'
                  sh 'tidy -q -e *.html'
              }
         }        
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-2',credentials:'Udacity_Jenkins') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'anandnk-jenkins-pipeline-bucket')
                  }
              }
         }
     }
}
