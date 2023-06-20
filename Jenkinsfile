pipeline {
    agent any
    parameters {
        string(name:"branch", defaultValue:"fromUpstream", description:"Branch to checkout project")
    }
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
                build job: 'DEV_pipeline_down', parameters: [string(name: 'branch', value: "${params.branch}")]
            }
        }
    }

    post {
        failure {
            echo "Failed stage "
        }
    }
}
