def updateCommitStatus(body){
    sh '''
        curl -L \
    -X POST \
    -H "Accept: application/vnd.github+json" \
    -H "Authorization: Bearer ${gitToken}" \
    -H "X-GitHub-Api-Version: 2022-11-28" \
    https://api.github.com/repos/Ranjith236838/test-jenkins/statuses/${sha1} \
    -d ${body}
    '''
}

def getJson(context, state, description){
    def result = "{\"state\":${state},\"target_url\":\"https://example.com/build/status\",\"description\":${description},\"context\":${context}}"
    return result
}

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
                    body = getJson("clean", "success", "Cleaning Succeeded")
                    echo "${body}"
                    updateCommitStatus($body)
                }
                failure{
                    echo "failure"
                    body = getJson("clean", "failure", "Cleaning failed")
                    echo "${body}"
                    updateCommitStatus($body)
                }
            }
        }
    }
}
