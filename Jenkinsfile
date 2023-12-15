pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    sh 'docker-compose -f pwd.yml down'
                    // sh 'docker-compose -f pwd.yml rm'
                    // sh 'docker-compose -f pwd.yml up -d'
                    sh 'docker rm $(docker ps -aq)'
                }
            }
        }
    }

    // post {
    //     always {
    //         script {
    //             // Use the 'dockerCompose' step to bring down servicesssss
    //             dockerCompose(
    //                 dockerComposeFile: 'docker-compose -f pwd.yml',
    //                 downOptions: ' --volumes'
    //             )
    //         }
    //     }
    // }
}

