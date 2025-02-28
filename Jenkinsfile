pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This checks out the code from the repository.
                bat 'rmdir /q /s MySoftware'
                bat 'git clone "https://github.com/Walrusil/MySoftware.git"'
                // In Linux: sh 'git clone https://github.com/Walrusil/MySoftware.git'
                // git(url: 'https://github.com/Walrusil/MySoftware.git', branch: 'main')
            }
        }
        stage('Run Script') {
            steps {
                script {
                    echo "Running MySoftware.py..."
                    // sh 'python MySoftware.py'
                    bat 'python MySoftware.py'
                }
            }
        }
    }
}