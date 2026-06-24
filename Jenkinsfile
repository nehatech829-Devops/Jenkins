pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {
                    if (params.BRANCH == 'main') {
                        sh '''
                        cp -r main/index.txt /var/lib/jenkins/deploy/main/

                        echo "===== MAIN OUTPUT ====="
                        cat /var/lib/jenkins/deploy/main/index.txt
                        '''
                    } else {
                        sh '''
                        cp -r dev/index.txt /var/lib/jenkins/deploy/dev/

                        echo "===== DEV OUTPUT ====="
                        cat /var/lib/jenkins/deploy/dev/index.txt
                        '''
                    }
                }
            }
        }
    }
}
