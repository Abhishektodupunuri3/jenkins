pipeline {
    agent any

    environment {
        ENV_URL         = "pipeline.google.com"
        SSH_CRED        = credentials('SSH_CRED')
    }
    
    stages {

       
        
        stage('stage one') {

        steps {

                 sh '''echo devops
                 echo aws 
                 echo b54
                 echo Nme of the URL is ${ENV_URL}'''
        }

        }



         
        stage('stage twoe'){

        steps {

            echo "This is stage two"
            echo "Nme of the URL is ${ENV_URL}"
        }
        }

         
        stage('stage three'){

                steps {

            echo "This is stage three"
             echo "Nme of the URL is ${ENV_URL}"
                }
      }
    }


}