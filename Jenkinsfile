pipeline {
    agent any 

    environment {
        ENV_URL          = "pipeline.google.com"           //PIPELINE VARIABLE
        SSHCRED          = credentials('SSH_CRED')
    }
    
    stages {

           stage ('stage one') {
         steps {
                    sh '''
                          echo devops training
                          echo Aws training
                          echo b54
                          echo Name of the URL is ${ENV_URL}
                          env
                    '''
               }
        }

             stage ('stage two') {
                 environment {
                               ENV_URL = "stage.google.com"           //STAGE VARIABLE
                           }
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