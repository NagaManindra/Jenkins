pipeline {
    agent any

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
