pipeline {
    agent none
    stages {
        stage('stage 1') {
            agent{ label 'linux'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                sh 'git --version'
            }
        }

        stage('stage 2') {
            agent{ label 'window'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                echo "new commit"
                bat """ cd C:\\Program Files\\Git\\bin
                        C:
                        git --version"""
            }
        }
        
    }
}
