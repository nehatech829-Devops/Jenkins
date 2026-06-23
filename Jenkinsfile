pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {

                    if (env.BRANCH_NAME == 'main') {
                        bat '''
                        xcopy /E /Y /I * C:\\deploy\\main\\
                        '''
                    }

                    if (env.BRANCH_NAME == 'dev') {
                        bat '''
                        xcopy /E /Y /I * C:\\deploy\\dev\\
                        '''
                    }

                }
            }
        }
    }
}
