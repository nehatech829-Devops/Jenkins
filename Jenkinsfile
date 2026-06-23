pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {

                    if (env.BRANCH_NAME == 'main') {
                        sh '''
                        mkdir -p ~/deploy/main
                        cp -r * ~/deploy/main/
                        '''
                    }

                    if (env.BRANCH_NAME == 'dev') {
                        sh '''
                        mkdir -p ~/deploy/dev
                        cp -r * ~/deploy/dev/
                        '''
                    }

                }
            }
        }
    }
}
