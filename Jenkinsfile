pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    dockerCompose(
                        dockerComposeFile: 'docker-compose.yml',
                        upOptions: ' -d'
                    )
                }
            }
        }
    }

    post {
        always {
            script {
                dockerCompose(
                    dockerComposeFile: 'docker-compose.yml',
                    downOptions: ' --volumes'
                )
            }
        }
    }
}
