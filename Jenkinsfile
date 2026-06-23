pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: "${BRANCH}",
                    url: 'https://github.com/nehatech829-Devops/Jenkins.git'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (params.BRANCH == 'main') {
                        sh '''
                        mkdir -p /var/lib/jenkins/deploy/main
                        cp -r * /var/lib/jenkins/deploy/main/
                        '''
                    } else if (params.BRANCH == 'dev') {
                        sh '''
                        mkdir -p /var/lib/jenkins/deploy/dev
                        cp -r * /var/lib/jenkins/deploy/dev/
                        '''
                    }
                }
            }
        }
    }
}
