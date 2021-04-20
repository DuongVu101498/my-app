pipeline {
    agent none
    stages {
        stage('stage 1') {
            agent{ label 'linux'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
            }
        }
        stage('stage 2') {
            agent{ label 'window'}
            tools {
                git 'git-for-windows-2.31.1-64-bit'
            }
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
            }
        }
        
    }
}
