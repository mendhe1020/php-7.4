pipeline {
    agent any

    stages {

        stage("Code") {
            steps {
                script {
                    // Determine the branch name dynamically
                    def branchName = sh(script: 'git rev-parse --abbrev-ref HEAD', returnStdout: true).trim()
                    echo "Current branch: ${branchName}"
                    
                    git url: "https://github.com/mendhe1020/php-7.4.git", branch: branchName
                }
            }
        
        }
        }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed. Please check logs for details.'
        }
    }
}
