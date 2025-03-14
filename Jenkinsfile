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
                    npm run build
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
                    
                    cd jenkins-demo
                    npm test

                '''
            }
        }
    }
}
