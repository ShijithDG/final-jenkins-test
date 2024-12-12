
pipeline{
    agent any

    stages{
        stage('Git Checkout'){
            steps{
                git branch : 'main' , url :'https://github.com/ShijithDG/final-jenkins-test.git'
            }
        }
        stage('running Script'){
            steps{
                sh 'python3 add.py'
                echo 'success'
            }
        }
    }
    post{
        always{
            echo 'cleaning'
        }
        failure{
            echo 'failed '
        }
        success{
            echo 'success'
        }
    }
}
