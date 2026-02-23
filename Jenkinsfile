pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'This is the build stage building my app'
                sh '''
                    npm --version
                    node --version
                    ls -l
                    npm ci
                    npm run build

                    ls -l
                '''
            }
        }
    }
}
