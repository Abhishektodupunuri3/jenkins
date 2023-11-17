pipeline {
    agent any 

    environment {
        ENV_URL          = "pipeline.google.com"           //PIPELINE VARIABLE
        SSHCRED          = credentials('SSH_CRED')
    }
         parameters {
                               string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                               text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
                               booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
                               choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
                               password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
                    }
      
     triggers { pollSCM('*/1 * * * *') }

    
    stages {

           stage ('stage one') {
         steps {
                    sh '''
                          echo devops training
                          echo Aws training
                          echo b54
                          echo Name of the URL is ${ENV_URL}
                          env
                          sleep 10
                    '''
               }
        }

             stage ('stage two') {
                 environment {
                               ENV_URL = "stage.google.com"           //STAGE VARIABLE
                           }
                 //input {
                           //message "Should we continue?"
                           //   ok "Yes, we should."
                         //        submitter "alice,bob"
                       //parameters {
                       //                  string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                     //           }
                   // }           
                  steps {
                          echo "This is stage two"
                          echo "Name of the URL is ${ENV_URL}"
                          sleep 10
                        }
        }
            stage ('stage three') {
                when{   
                        branch 'dev'
                        changeset "**/*.js"
                    }
         steps {
                sh'''
                   echo "This is stage three"
                   echo "name of the URL is ${ENV_URL}"
                   echo -e "\\e[31m hi ABHISHEK luv u sarikha"
                  
                '''
            }
        }
             stage ('stage four') {
              steps {
                sh'''
                   echo "This is stage foure"
                   echo "name of the URL is ${ENV_URL}"
                   echo -e "\\e[31m hi sunny luv u chinky"
                   sleep 10
                  
                '''
            }
        }
    }

}