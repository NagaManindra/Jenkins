pipeline {
    agent {
        docker {
            image "node:18-alpine"
            reuseNode yes
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
                    test -f jenkins-demo/build/index.html
                '''
            }
    }
}
