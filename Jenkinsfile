pipeline {
    agent none
    stages {
        stage('Test') {
            agent {
                docker {
                    image 'grihabor/pytest'
                }
            }
            steps {
                sh 'pyvtest -v --junit-xml test-reports/results.xml sources/test_calc.py'
            }
            post {
                always {
                    junit "test-reports/results.xml"
                }
            }
        }
        }
    }
}
