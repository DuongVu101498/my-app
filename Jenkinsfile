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
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                echo "new commit"
                echo "new commit fixed"
            }
        }
        
    }
}
