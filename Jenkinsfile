pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    sh 'docker-compose -f pwd.yml down'
                    sh 'docker-compose -f pwd.yml up -d'
                }
            }
        }
    }

    // post {
    //     always {
    //         script {
    //             // Use the 'dockerCompose' step to bring down servicesssssssss
    //             dockerCompose(
    //                 dockerComposeFile: 'docker-compose -f pwd.yml',
    //                 downOptions: ' --volumes'
    //             )
    //         }
    //     }
    // }
}

