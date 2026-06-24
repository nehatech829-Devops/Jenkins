pipeline {
    agent any

    parameters {
        choice(
            name: 'BRANCH',
            choices: ['main', 'dev'],
            description: 'Select branch'
        )
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    url: 'https://github.com/nehatech829-Devops/Jenkins.git'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (params.BRANCH == 'main') {
                        sh 'cp -r main/* /var/lib/jenkins/deploy/main/'
                    } else {
                        sh 'cp -r dev/* /var/lib/jenkins/deploy/dev/'
                    }
                }
            }
        }
    }
}
