pipeline {
    agent none
    parameters {
      string(name: 'TESTPARAM', defaultValue: 'default value', description: 'A parameter passed to the Python script')
    }
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:2-alpine'
                }
            }
            steps {
                sh "python sources/run.py '${params.TESTPARAM}'"
            }
        }
    }
}
