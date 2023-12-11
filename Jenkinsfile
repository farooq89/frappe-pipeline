pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    script {
                    sh 'docker-compose -f pwd.yml up -d'
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
