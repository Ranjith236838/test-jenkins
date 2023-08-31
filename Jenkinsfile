pipeline{
    agent any
    stages{
        stage('Test'){
            steps{
                sh 'whoami'
                echo "${ghprbPullLink}"

                notifyGithub status: 'SUCCESS', message: 'Build was successful', url: ${ghprbPullLink}
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
