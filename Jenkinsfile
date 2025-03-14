pipeline {
    agent any

    stages {
        stage('ReactApp') {
            steps {
                sh'''
                    npm install --force
                    npm start
                '''    
            }
        }
    }
}
