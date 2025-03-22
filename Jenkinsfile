pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID = credentials('account_Id') 
        AWS_DEFAULT_REGION="us-west-1"     
    }
        
    stages {
        stage('Infrastructure Deployment') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('aws.access.key_id')
             AWS_SECRET_ACCESS_KEY = credentials('Secret_access_key')
           }
           steps {
              script {
                  sh "terraform init"
                  sh "terraform validate"
                  sh "terraform plan"
                  sh "terraform ${action} --auto-approve"
            }
        }
               
     }
    }
    
}
