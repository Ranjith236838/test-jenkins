pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Your build steps here
                echo "Hello World"
            }
        }
    }

    post {
        always {
            // This post-build section will always run, regardless of the build result

            script {
                // Notify GitHub about the build result using the GitHub Notifier Plugin
                currentBuild.resultIsBetterOrEqualTo('SUCCESS') ?
                        githubNotify(message: 'Build was successful', status: 'SUCCESS') :
                        githubNotify(message: 'Build failed', status: 'FAILURE')
            }
        }
    }
}

def githubNotify(def notifyMap) {
    step([
        $class: 'GitHubCommitNotifier',
        statusResult: notifyMap.status,
        commentBody: notifyMap.message,
        result: currentBuild.currentResult
    ])
}
