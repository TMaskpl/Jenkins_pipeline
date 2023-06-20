pipeline {
    agent any
    options {
        ansiColor('vga')
    }
    stages {
        stage('Git clone...') {
            steps {
                script {
                    echo 'Clone repository...'
                }
            }
        }

        stage('Check system...') {
            steps {
                script {
                    echo 'Check system...'
                }
            }        
        }

        stage('Create snapshot...') {
            steps {
                script {
                    echo 'Create snapshot...'
                }
            }
        }
        
        stage('Update Windows ...') {
            steps {
                script {
                    echo 'Update Windows...'
                }
            }
        }

        stage('Remove snapshot...') {
            steps {
                script {
                    echo 'Remove snapshot...'
                }
            }
        }
    }

    post {
        failure {
            echo "Failed stage name: ${FAILED_STAGE}"
            slackSend (color: '#FF0000', channel: 'tmaskpl', message: """FAILED_STAGE: Job "${env.STAGE_NAME} ${env.JOB_NAME} [${env.BUILD_NUMBER}]" (${env.BUILD_URL})""")
        }
    }
}
