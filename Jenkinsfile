pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    sh 'docker-compose -f pwd.yml down'
                    // sh 'docker rm $(docker ps -aq)'123
                    sh 'docker-compose -f pwd.yml up -d'
                }
            }
        }
    }

    post {
        always {
            script {
                slackSend(channel: '#atd-notifications', color: 'good', message: "Build completed successfully!")
            }
        }
        failure {
            script {
                // test123123
                slackSend(channel: '#atd-notifications', color: 'danger', message: "Build failed!")
            }
        }
    }
}


