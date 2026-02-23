pipeline {
    agent any

    stages {
        /*
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
        } */
        stage('Test') {
            steps {
                echo 'Testing to see if the index.html exits'
                sh 'test -f build/index.html'
            }
        }
        stage('Deploy') {
            agent {
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'This is the build stage building my app'
                sh '''
                    npm install netlify-cli@20.1.1 --save-dev
                    npx netlify --version

                '''
            }
        } 
    }
}
