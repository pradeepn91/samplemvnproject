pipeline {
         agent any
         stages {
                 stage('One') {
                 steps {
                     scm{

                         git{'git@github.com:pradeepn91/samplemvnproject.git'}
                     }
                     echo 'Hi, this is Zulaikha from edureka'
                 }
                 }
                 stage('Two') {
                 steps {
                    input('Do you want to proceed?')
                     maven {
                        goals('clean')
                        goals('verify')}
                        
                 }
                 }
                 stage('Three') {
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
                              //agent {
                                //    docker {
                                     //       reuseNode true
                                      //      image 'ubuntu'
                                       //    }
                                   // }
                              steps {
                                echo "Running the integration test..."
                              }
                           }
                           }
                           }
              }
}
