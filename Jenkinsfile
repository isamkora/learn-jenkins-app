pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    chown -R 102:105 "/.npm"
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                    echo "First run in a repo"
                '''
            }
        }
    }
}
