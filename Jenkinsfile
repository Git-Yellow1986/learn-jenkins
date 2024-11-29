// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building the project...'
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo 'Running tests...'
//             }
//         }

//         stage('Deploy') {
//             steps {
//                 echo 'Deploying the application...'
//             }
//         }
//     }
// }

pipeline {
   agent {
        label 'AGENT-1'
   }
//   options {
//         // Timeout counter starts AFTER agent is allocated
//         timeout(time: 10, unit: 'SECONDS')
//          disableConcurrentBuilds() 
    stages {
        stage('Building code'){
            steps {
                echo 'Matthews is Building  code'
               // sh 'sleep 10'
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
    }
    post {
        always{
            echo "Always running process"
            //deleteDir()
        }
    
        success{
            echo "send succes notification"
        }
        failure{
        echo "failure notifications"
        }
    }
}