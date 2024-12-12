
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
                sh '''
                    sudo apt-get update
                    sudo apt-get install -y unzip curl
                    rm -rf aws cliv2.zip aws/
                    sudo curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
                    unzip awscliv2.zip
                    sudo ./aws/install --update
                '''
                echo 'success'
                sh 'aws --version'
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
