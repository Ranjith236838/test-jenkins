pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Your build steps here
                sh 'whoami'
            }
            
            post {
                success {
                    githubChecks([description: 'Build passed', context: 'build'])
                }
                failure {
                    githubChecks([description: 'Build failed', context: 'build', conclusion: 'failure'])
                }
            }
        }
        
        stage('Test') {
            steps {
                // Your test steps here
                cleanWs()
            }
            
            post {
                always {
                    githubChecks([description: 'Tests completed', context: 'test'])
                }
            }
        }
        
        // Add more stages
    }
}
