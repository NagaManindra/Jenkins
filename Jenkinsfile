pipeline {
    agent {
        docker {
            image "node:18-alpine"
            reuseNode true
        }
    }

    stages {
        stage('ReactApp') {
            steps {
                sh'''
                    cd jenkins-demo
                    npm install --force
                    npm start &
                    sleep 10
                '''    
            }
        }

        stage('test') {
            steps {
                sh'''
                    if [ -e jenkins-demo/build/index.html ]; then
                        echo "file exists"
                    else
                        echo "file not exists"
                    fi
                    cat jenkins-demo/build/index.html
                    cd jenkins-demo
                    npm test

                '''
            }
        }

        stage('E2E'){
            agent{
                docker{
                    image "mcr.microsoft.com/playwright:v1.51.1-noble"
                }
            }
            steps{
                sh '''
                    cd jenkins-demo
                    npm i -g serve
                    serve -s build &
                    sleep 10
                    npm playwright test
                '''
            }
        }
    }
    post{
        always{
            echo "completed"
        }
    }
}
