pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    sh 'docker-compose -f pwd.yml down'
                    // sh 'docker rm $(docker ps -aq)'
                    sh 'docker-compose -f pwd.yml up -d'
                }
            }
        }
    }

    post {
        always {
            script {
                // This block will be executed always, regardless of the build result
                slackSend(channel: '#atd-notifications', color: 'good', message: "Build completed successfully!")
            }
        }
        failure {
            script {
                // This block will be executed only if the build failsss
                slackSend(channel: '#atd-notifications', color: 'danger', message: "Build failed!")
            }
        }
    }
}


