pipeline {
    agent any 
    environment {
        RELEASE='20.04'
    }
        stages {
            stage('Build') {
            agent any    
            environment {
                LOG_LEVEL='info'
            }
            steps {
                echo "Release Version: $RELEASE, LOG Level ${LOG_LEVEL}"
            }
        }
        
         stage('Test') {
            steps {
               echo "Testing Release Version: $Release"
            }
        }
        
         stage('Deploy') {
                input {
                message 'Deploy?'
                ok 'Do it!'
                parameters {
                    string(name: 'TARGET_ENVIRONMENT', defaultValue: 'PROD', description: 'Target deployment Environment')
                }
            }     
            
            steps {
                echo "Deploying Release Version $RELEASE to environment ${TARGET_ENVIRONMENT}"
            }
         }
        }
            
            post{
                always {
                    echo 'Prints whether deploy happened or not, success or failure'
                }
            }
}
            
            
