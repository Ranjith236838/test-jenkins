void setBuildStatus(String message, String state) {
  step([
      $class: "GitHubCommitStatusSetter",
      reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://github.com/Ranjith236838/test-jenkins.git"],
      contextSource: [$class: "ManuallyEnteredCommitContextSource", context: "default"],
      errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
      statusResultSource: [ $class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]] ]
  ]);
}



pipeline{
    agent any
    stages{
        stage('Test'){
            steps{
                sh 'whoami'
                echo "${ghprbPullLink}"

                //githubNotify description: "Build is successfull", status: 'SUCCESS', context: 'Build Status', credentialsId: "github-pat", repo: "https://github.com/Ranjith236838/test-jenkins.git", sha: "${sha1}"         
                
            }
                    
            post{
                success{
                    echo "Hello World"
                    setBuildStatus("Build succeeded", "SUCCESS");

                }
                failure{
                    echo "Failure"
                    setBuildStatus("Build Failed", "Failed");

                }
            }
        }
        stage('SonarScan'){
            steps{
                sh 'whoami'
            }
            post{
                success{
                    setBuildStatus("SonarScan succeeded", "SUCCESS")
                }
                failure{
                    setBuildStatus("SonarScan failed", "FAIL")
                }
            }
        }
    }
}
