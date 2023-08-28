pipeline{
    agent any
    stages{
        stage('Clean & Checkout'){
            steps{
                sh 'echo "Hello World"'
            }
            post{
                success {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'SUCCESS'
                        }
                    }
                }
                failure {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'FAILURE'
                        }
                    }
                }
            }
        }
        stage('Title Check'){
            steps{
                sh 'whoami'
            }
            post{
                success {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'SUCCESS'
                        }
                    }
                }
                failure {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'FAILURE'
                        }
                    }
                }
            }
        }
        stage('CodeQL Scan'){
            steps{
                sh 'whoami'
            }
            post{
                success {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'SUCCESS'
                        }
                    }
                }
                failure {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'FAILURE'
                        }
                    }
                }
            }
        }
        stage('SonarQube'){
            steps{
                sh 'whoami'
            }
            post{
                success {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'SUCCESS'
                        }
                    }
                }
                failure {
                    script {
                        githubStatus {
                            context: 'Test',
                            description: 'Tests passed'
                            state: 'FAILURE'
                        }
                    }
                }
            }
        }
    }
}
