pipeline {
    agent any 

    environment {
        ENV_URL = "pipeline.google.com"
    }
    
    stages {

           stage ('stage one') {
         steps {
                     sh '''
                     echo devops training
                     echo Aws training
                     echo b54
                     echo Name of the URL is ${ENV_URL}
                     '''
               }
        }

             stage ('stage two') {
         steps {
                echo "This is stage two"
                 echo "Name of the URL is ${ENV_URL}"
            }
        }
            stage ('stage three') {
         steps {
                echo "This is stage three"
            }
        }
    }

}