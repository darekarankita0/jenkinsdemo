pipeline {
    agent any
    tools{
        maven 'maven3'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application'
                echo 'sh mvn install'
            }
        }
        stage('Test') {
            when{
                expression{
                    env.BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo 'Testing the application'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application'
            }
        }
    }
}

post{
    always{
      echo 'send emails'
    }
    success{
      echo 'Process completed'
    }
    failure{
      echo 'Process failed'
    }
    }

