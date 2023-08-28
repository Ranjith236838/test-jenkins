pipeline{
    agent any
    stages{
        stage('Test'){
            steps{
                sh 'whoami'
            }
            post{
                success{
                    echo "Hello World"
                }
                failure{
                    echo "Failure"
                }
            }
        }
    }
}
