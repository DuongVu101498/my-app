pipeline {
    agent none
    stages {
        stage('stage 1') {
            agent{ label 'linux'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                sh ''' pwd
                       touch file2.txt
                       ls '''
            }
        }

        stage('stage 2') {
            agent{ label 'window'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                echo "new commit 2"
                bat 'git --version'
            }
        }
        
    }
}
