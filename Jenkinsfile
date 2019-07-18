pipeline {
         agent any
         stages {
                 stage('Welcome Message') {
                 steps {
                     echo 'Hi, this is Raja from Tieto'
                 }
                 }
                 stage('Proceed') {
                 steps {
                    input('Would you like to proceed further')
                 }
                 }
                 stage('Ifyes') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "Hello"
                 }
                 }
                 stage('Four') {
                 parallel { 
                            stage('Unit Test') {
                           steps {
                                echo "Running the unit test..."
                           }
                           }
                            stage('Integration test') {
                              agent {
                                    docker {
                                            reuseNode true
                                            image 'ubuntu'
                                           }
                                    }
                              steps {
                                echo "Running the integration test..."
                              }
                           }
                           }
                           }
              }
}