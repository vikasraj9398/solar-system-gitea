pipeline{
    agent any
    tools {
        nodejs 'node-20-6-0'
    }
    stages {
        stage('install dependences') {
            steps {
                sh 'npm install --no-audit';
            }
        }
        //stage('npm dependences audit') {
        //    steps {
        //        sh '''
        //        npm audit --audit-level=critical 
        //        echo $?
        //        ''';
        //    }
        //}
        stage('owasp dependence check') {
            steps {
                dependencyCheck additionalArguments:
                --scan \'./\'
                --out \'./\'
                --format \'ALL\'
                --prettyPrint''', odcInstallation: 'OWASP-DepCheck-10'
            }
        }
    }
}
