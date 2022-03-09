pipeline {
  agent any
  tools {
    terraform 'Terraform11'
   }

  stages {
      stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
      stage ('Terraform Init'){
        steps{
          sh 'terraform init'  
        }
      }
     stage ('Terraform Plan'){
        steps{
          sh 'terraform plan'  
        }
      }
     stage ('Terraform Apply'){
        steps{
          sh 'terraform apply --auto-approve'  
        }
      }
  }
}