pipeline {
   agent {
        label 'AGENT-1'
   }
   options {
      timeout(time: 10, unit: 'SECONDS')
       disableConcurrentBuilds()  
  }
        
  parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
  }
    stages {
        stage('Building code'){
            steps {
                echo 'Matthews is Building  code'
                 //sh 'sleep 10'
            }
        }
        stage ('Testing code'){
            steps {
                echo 'Madhu is Testing code'
            }
        }
        stage('Deploying code'){
            steps {
                echo 'Lalitha is Deploying code'
            }
        }
        stage ('Print params'){
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        
        stage ('Approval'){
                input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
        }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        
    }
    post {
        always{
            echo "Always running process"
            deleteDir()
        }
    
        success{
            echo "send succes notification"
        }
        failure{
        echo "failure notifications"
        }
    }
}