def updateCommitStatus(context, state, description){
    sh '''
        curl -L \
    -X POST \
    -H "Accept: application/vnd.github+json" \
    -H "Authorization: Bearer ${gitToken}" \
    -H "X-GitHub-Api-Version: 2022-11-28" \
    https://api.github.com/repos/Ranjith236838/test-jenkins/statuses/${sha1} \
    -d "{\"state\":${state},\"target_url\":\"https://example.com/build/status\",\"description\":${description},\"context\":${context}}"
    '''
}

// def getJson(context, state, description){
//     def result = "{\"state}"
// }

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
                    updateCommitStatus("clean", "success", "Cleaning Succeeded")
                }
                failure{
                    echo "failure"
                    updateCommitStatus("clean", "failure", "Cleaning failed")
                }
            }
        }
    }
}
