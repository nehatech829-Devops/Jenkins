pipeline {
    agent any

    parameters {
        choice(
            name: 'BRANCH',
            choices: ['main', 'dev', 'test'],
            description: 'Select branch to deploy'
        )
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    credentialsId: 'GitHub Deploy',
                    url: 'git@github.com:nehatech829-Devops/Jenkins.git'
            }
        }

        stage('Display Content') {
            steps {
                script {
                    echo "Current Branch: ${params.BRANCH}"

                    if (params.BRANCH == 'main') {
                        sh '''
                        echo "===== MAIN BRANCH ====="
                        cat main/index.txt
                        '''
                    }
                    else if (params.BRANCH == 'dev') {
                        sh '''
                        echo "===== DEV BRANCH ====="
                        cat dev/index.txt
                        '''
                    }
                    else if (params.BRANCH == 'test') {
                        sh '''
                        echo "===== TEST BRANCH ====="
                        cat test/index.txt
                        '''
                    }
                }
            }
        }
    }
}
