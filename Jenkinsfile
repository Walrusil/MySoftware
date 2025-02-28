pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This checks out the code from the repository.
                bat 'git clone "https://github.com/Walrusil/MySoftware.git"'
                // In Linux: sh 'git clone https://github.com/Walrusil/MySoftware.git'
                // git(url: 'https://github.com/Walrusil/MySoftware.git', branch: 'main')
            }
        }
        stage('Run Script') {
            steps {
                script {
                    // Jenkins sets BRANCH_NAME for multibranch pipelines.
                    if (env.BRANCH_NAME == 'main') {
                        // For the master branch, simply run the script.
                        echo "Running MySoftware.py on master branch..."
                        // sh 'python MySoftware.py'
                        bat 'python MySoftware.py'
                    } else {
                        echo "Branch ${env.BRANCH_NAME} does not trigger any specific action."
                    }
                }
            }
        }
    }
}