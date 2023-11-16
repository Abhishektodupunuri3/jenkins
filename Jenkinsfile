pipeline {
    agent any

    environment {
        ENV_URL         = "pipeline.google.com"
        SSHCRED         =  credentials('SSH_CRED')
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

       
        
        stage('stage one') {

        steps {

                 sh '''echo devops
                 echo aws 
                 echo b54
                 echo Nme of the URL is ${ENV_URL}
                 
                 env
                     '''
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

                      sh ''' 
                echo "This is stage three"
                echo "Name of the URL is ${ENV_URL}"
                echo -e "\\e[31m Hai"
                

                ''' 

                }
      }
    }


}