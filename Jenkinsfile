pipeline {
  agent any
  tools {
    terraform 'Terraform11'
   }

  stages {
     stage('Pull') {              
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/soumayaMb/Terraform--MS-Azure.git']]])
                }
            }
			}         

    }
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