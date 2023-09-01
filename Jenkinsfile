def callcurl(state, context, description, targetUrl) {
    def curlCommand = """
        curl -L \\
            -X POST \\
            -H 'Accept: application/vnd.github+json' \\
            -H 'Authorization: Bearer ${gitToken_PSW}' \\
            -H 'X-GitHub-Api-Version: 2022-11-28' \\
            https://api.github.com/repos/Ranjith236838/test-jenkins/statuses/${sha1} \\
            -d '{"state":"${state}","target_url":"${BUILD_URL}","description":"${description}","context":"${context}"}'
    """

    return sh(script: curlCommand, returnStatus: true)
}

pipeline{
    agent any
    environment{
        gitToken = credentials('github-pat')
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
                    callcurl("success", "clean", "Cleaning Succeeded", "url")
                    // body = getJson("clean", "success", "Cleaning Succeeded")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
                failure{
                    echo "failure"
                    callcurl("fail", "clean", "Cleaning failed", "url")
                    // body = getJson("clean", "failure", "Cleaning failed")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
            }
        }
        stage('Build'){
            steps{
                script{
                    echo "Building"
                }
            }
            post{
                success{
                    echo "success"
                    callcurl("success", "build", "building Succeeded", "url")
                    // body = getJson("clean", "success", "Cleaning Succeeded")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
                failure{
                    echo "failure"
                    callcurl("fail", "build", "building failed", "url")
                    // body = getJson("clean", "failure", "Cleaning failed")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
            }            
        }
        stage('Test'){
            steps{
                script{
                    echo "Building"
                }
            }
            post{
                success{
                    echo "success"
                    callcurl("success", "test", "testing Succeeded", "url")
                    // body = getJson("clean", "success", "Cleaning Succeeded")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
                failure{
                    echo "failure"
                    callcurl("fail", "test", "testing failed", "url")
                    // body = getJson("clean", "failure", "Cleaning failed")
                    // echo "${body}"
                    // updateCommitStatus($body)
                }
            }            
        }
    }
}
