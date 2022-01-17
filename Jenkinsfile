
pipeline {
    agent any
    environment {
        name = 'sriram'
    }
    stages {
        stage('Build') {
            steps {
                  echo "hello worlds"
                
            }
        }
        stage('Environment Variables') {
            environment {
                username = 'myusername'
            }
            steps {
                echo  "${BUILD_ID}"
                echo   "${name}"
                echo  "${username}"
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
               
            }
        }
       stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we Should"
            }
        stage('Deploy'){
            steps {
                echo 'deploy on prod'
            }
        }
      }
    post{
        always { 
            echo 'I will always say Hello again!'
        }
        
    }
}
