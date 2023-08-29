pipeline{
    agent any
    stages{
        stage('Test'){
            steps{
                sh 'whoami'
                cleanWs()
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
