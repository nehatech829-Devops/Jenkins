pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {

                    def branch = sh(
                        script: "git rev-parse --abbrev-ref HEAD",
                        returnStdout: true
                    ).trim()

                    echo "Current Branch: ${branch}"

                    if (branch == "main") {

                        sh '''
                        cp -r main/index.txt /var/lib/jenkins/deploy/main/
                        echo "===== MAIN OUTPUT ====="
                        cat /var/lib/jenkins/deploy/main/index.txt
                        '''

                    } else if (branch == "dev") {

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
