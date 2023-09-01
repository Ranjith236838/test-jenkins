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

                        githubNotify(
                            account: 'Ranjith236838', context: 'Final Test', 
                            credentialsId: 'github-pat', description: 'This is a shorted example',  
                        repo: 'https://github.com/Ranjith236838/test-jenkins', sha: 'd75c3cc28e755dbecb3dd9fc4f4b58c4c1e8b6c4 ', 
                        status: 'SUCCESS', targetUrl: 'https://example.com'
                        
                        )

                }
                failure {
                        echo "failed"
               //     githubNotify description: 'This is a shorted example',  status: 'SUCCESS'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Your test steps here
                cleanWs()
            }
            // post {
            //     success {

            //             githubNotify description: 'This is a shorted example',  status: 'SUCCESS'

            //     }
            //     failure {

            //         githubNotify description: 'This is a shorted example',  status: 'SUCCESS'
            //     }
            // }
        }
        
        // Add more stages
    }
}
