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
    label 'AGENT-11'
   }

    stages {
        stage('Building code'){
            steps {
                echo 'Matthews is Building  code'
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