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
      
    // triggers { pollSCM('*/1 * * * *') }

    
    stages {
                 stage('Parallel Stages') {
            parallel {
                stage('In Parallel 1') {
                        steps {
                            echo "In Parallel 1"
                            sleep 1
                            
                        }
                    }
                stage('In Parallel 2') {
                        steps {
                            echo "In Parallel 2"
                            sleep 1
                    }
                }
                stage('In Parallel 3') {
                        steps {
                            echo "In Parallel 3"
                            sleep 1
                    }
                }
            }
        }

           stage ('stage one') {
         steps {
                    sh '''
                          echo devops training
                          echo Aws training
                          echo b54
                          echo Name of the URL is ${ENV_URL}
                          env
                          sleep 1
                    '''
               }
        }

             stage ('stage two') {
                 environment {
                               ENV_URL = "stage.google.com"           //STAGE VARIABLE
                           }
                 /*input {
                           message "Should we continue?"
                           ok "Yes, we should."
                           submitter "alice,bob"
                    parameters {
                                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                                }
                    }  */         
                  steps {
                          echo "This is stage two"
                          echo "Name of the URL is ${ENV_URL}"
                          sleep 1
                        }
        }
            stage ('stage three') {
                when{   
                       anyOf {
                                branch 'dev'
                                changeset "**/*.js" 
                            }
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
                   sleep 1
                  
                '''
            }
        }
            /*  post {
                      always {
                                cleanWs()
                            }
                   }*/
    
    }

}