pipeline {
    agent any

    stages {

        stage('Deploy Dev') {
            when {
                branch 'dev'
            }
            steps {
                sh '''
                cp -r dev/* /var/lib/jenkins/deploy/dev/
                '''
            }
        }

        stage('Deploy Main') {
            when {
                branch 'main'
            }
            steps {
                sh '''
                cp -r main/* /var/lib/jenkins/deploy/main/
                '''
            }
        }
    }
}
