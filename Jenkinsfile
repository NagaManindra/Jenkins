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
                    npm run build
                '''    
            }
        }
    }
}
