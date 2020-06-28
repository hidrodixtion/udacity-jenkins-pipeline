pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-southeast-1',credentials:'aws-static') {
                  sh 'echo "Uploading static site content to S3"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-jenkins-pipeline-bucket')
                  }
            }
        }
    }
}