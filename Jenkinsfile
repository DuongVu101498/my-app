pipeline {
    agent none
    stages {
        stage('stage 1') {
            agent{ label 'linux'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                sh ''' pwd
                       ls
                       set
                       printenv
                       '''
                script {
                     println "currentBuild.result = ${currentBuild.currentResult}"
                }
            }
        }
         stage('stage 2') {
            agent{ label 'linux'}
             stages{
                 stage('1'){
                     agent{ label 'linux'}
                     steps {
                       echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                       sh '''java --version'''
                       script {
                         def _Name = "Hello world!"
                         println "currentBuild.result = ${currentBuild.currentResult}"
                         println(_Name)
                       }
                     }
                  }
                 stage('2') {
                   agent{ label 'window'}
                     steps {
                        echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                        echo "new commit 2"
                        bat ''' cd
                            set'''
                         script {
                         println(_Name)
                       }
                     }
                 }
                 stage('3'){
                     agent{ label 'linux'}
                     steps {
                       echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                       sh '''java --version'''
                       script {
                         println(_Name)
                         println "currentBuild.result = ${currentBuild.currentResult}"
                       }
                     }
                  }
             }
        }
        stage('stage 3') {
            agent{ label 'window'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                echo "new commit 2"
                bat ''' cd
                        set'''
            }
        }
         stage('stage 4') {
            agent{ label 'k8s'}
            steps {
                echo "Running ${env.BUILD_ID} on ${env.NODE_NAME}"
                sh '''java --version
                      kubectl get services --all-namespaces'''
                script {
                         println "currentBuild.result = ${currentBuild.currentResult}"
                       }
            }
        }
    }
}
