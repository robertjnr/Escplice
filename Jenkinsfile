
pipeline {
    agent any
    environment {
        name = 'sriram'
    }
    parameters {
        string(name: 'person', defaultValue: 'Sriram', description: "Who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Hyderabad','bbsr'], description: "")
    }
    stages {
        stage('Run A command') {
            steps {
                bat '''
                ls
                date
                pwd
                '''
                
            }
        }
        stage('Environment Variables') {
            environment {
                username = 'myusername'
            }
            steps {
                bat 'echo  "${BUILD_ID}"'
                bat 'echo  "${name}"'
                bat 'echo  "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                bat 'echo "${name}"'
                bat 'echo  "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we Should"
            }
            
            steps {
                echo 'deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }
    post{
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Successs'
        }
    }
}
