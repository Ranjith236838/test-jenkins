pipeline{
    agent any
    stages{
        stage('Clean & Checkout'){
            steps{
                sh 'echo "Hello World"'
            }
            post{
                success {
                    echo "success"
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'SUCCESS'
                    //     }
                    // }
                }
                failure {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'FAILURE'
                    //     }
                    // }
                    echo "success"
                }
            }
        }
        stage('Title Check'){
            steps{
                sh 'whoami'
            }
            post{
                // success {
                //     script {
                //         githubStatus {
                //             context: 'Test',
                //             description: 'Tests passed'
                //             state: 'SUCCESS'
                //         }
                //     }
                echo "success"
                }
                failure {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'FAILURE'
                    //     }
                    // }
                    echo "success"
                }
            }
        }
        stage('CodeQL Scan'){
            steps{
                sh 'whoami'
            }
            post{
                success {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'SUCCESS'
                    //     }
                    // }
                    echo "success"
                }
                failure {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'FAILURE'
                    //     }
                    // }
                    echo "success"
                }
            }
        }
        stage('SonarQube'){
            steps{
                sh 'whoami'
            }
            post{
                success {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'SUCCESS'
                    //     }
                    // }
                    echo "success"
                }
                failure {
                    // script {
                    //     githubStatus {
                    //         context: 'Test',
                    //         description: 'Tests passed'
                    //         state: 'FAILURE'
                    //     }
                    // }
                    echo "success"
                }
            }
        }
    }

