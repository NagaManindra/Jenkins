pipeline {
    agent {
        docker {
            image "node:18-alpine"
        }
    }

    stages {
        stage('ReactApp') {
            steps {
                sh'''
                    cd jenkins-demo
                    npm install --force
                    npm start
                '''    
            }
        }
    }
}
