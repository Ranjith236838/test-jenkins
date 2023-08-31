pipeline{
    agent any
    stages{
        stage('Test'){
            steps{
                sh 'whoami'
                echo "${ghprbPullLink}"

                githubNotify description: "Build is successfull", status: 'SUCCESS', context: 'Build Status', sha: "${sha1}"
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
