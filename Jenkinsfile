pipeline{
    agent any 
    stages {
        stage('Lint HTML'){
            sh 'tidy -q -e *.html'
        }
        stage('Upload to AWS'){
            steps{
                withAWS(region:'ap-southeast-2',credentials:'aws-static'){
                    s3Upload(file:'index.html', bucket:'aws-static-edison',path:'index.html')
                }
            }
        }
    }
}