pipeline {
    agent any

    tools {
        nodejs 'node-20-6-0'
    }

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm install --no-audit'
            }
        }

        /*
        stage('NPM Dependency Audit') {
            steps {
                sh '''
                  npm audit --audit-level=critical || true
                '''
            }
        }
        */

        stage('OWASP Dependency Check') {
            steps {
                dependencyCheck(
                    additionalArguments: '''
                        --scan ./ 
                        --out ./ 
                        --format ALL 
                        --prettyPrint
                    ''',
                    odcInstallation: 'owasp-dependence-10-3'
                )
            }
        }
    }
}
