pipeline{
    agent any
    tools {
        nodejs 'node-20-6-0'
    }
    stages {
        stage('nodejs check') {
            steps {
                sh '''node -v && npm -v''';
            }
        }
    }
}
