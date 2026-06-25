pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {
                    echo "GIT_BRANCH = ${env.GIT_BRANCH}"

                    if (env.GIT_BRANCH.contains('main')) {

                        sh '''
                        cp -r main/index.txt /var/lib/jenkins/deploy/main/
                        echo "===== MAIN OUTPUT ====="
                        cat /var/lib/jenkins/deploy/main/index.txt
                        '''

                    } else if (env.GIT_BRANCH.contains('dev')) {

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
