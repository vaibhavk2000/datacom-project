pipeline {
    agent any

    triggers {
        // Equivalent to GitHub Actions: push and pull_request on main/master
        // Note: For PR triggers in Jenkins, you typically configure a Multibranch Pipeline 
        // with GitHub Branch Source plugin rather than relying solely on cron-like triggers.
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                // Equivalent to actions/checkout@v4
                checkout scm
            }
        }

        stage('Run Environment Check') {
            steps {
                // Equivalent to running shell commands with GitHub environment variables
                script {
                    def branchName = env.BRANCH_NAME ?: env.GIT_BRANCH ?: "Unknown"
                    def triggeredBy = env.BUILD_USER ?: env.BUILD_CAUSE ?: "System/Push"
                    
                    echo "Pipeline triggered by: ${triggeredBy}"
                    echo "Current Git branch: ${branchName}"
                }
            }
        }
    }
}
