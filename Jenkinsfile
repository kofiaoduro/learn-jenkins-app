pipeline {
    agent any

    stages {
        agent {
            docker{
                image 'node:18-alpine'
                reuseNode true
            }
        }
        stage('Build') {
            steps {
                echo 'This is the build stage building my app'
                sh '''
                    npm --version
                    node --version
                    ls -l
                    npm ci
                    npm build

                    ls -l
                '''
            }
        }
    }
}
