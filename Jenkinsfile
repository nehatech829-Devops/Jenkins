pipeline {
    agent any

    stages {

        stage('Display Branch Content') {
            steps {
                script {

                    def branch = env.GIT_BRANCH ?: ''

                    echo "Current Branch: ${branch}"

                    if (branch.contains('main')) {
                        sh '''
                        echo "===== MAIN BRANCH ====="
                        cat main/index.txt
                        '''
                    }
                    else if (branch.contains('dev')) {
                        sh '''
                        echo "===== DEV BRANCH ====="
                        cat dev/index.txt
                        '''
                    }
                    else if (branch.contains('test')) {
                        sh '''
                        echo "===== TEST BRANCH ====="
                        cat test/index.txt
                        '''
                    }
                    else {
                        echo "Branch not configured. Skipping..."
                    }
                }
            }
        }
    }
}
