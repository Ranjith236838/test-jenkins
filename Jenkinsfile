pipeline{
    agent any
    environment{
        gitToken = credentials('github-token')
    }

    stages{
        stage('Clean'){
            steps{
                script{
                    cleanWs()
                    checkout scm
                }
            }
            post{
                success{
                    echo "success"
                }
            }
        }
    }
}
