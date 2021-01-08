// this is a declarative pipeline example.

pipeline {
  agent any
    stages {
      stage('Stage1') {
        steps {
          echo "This is stage1"
          }
      }
      
      stage('Stage2') {
        steps {
        echo "This is build $BUILD_NUMBER"
      }
        
        stage('Stage3') {
          steps {
            chmod +x ./test.sh
            /bin/bash test.sh
          }
      }
        
   }
 }  
