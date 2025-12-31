pipeline{
    agent any

    stages {
        stage('nodejs check') {
            steps {
                sh '''node -v && npm -v''';
            }
        }
    }
}
