pipeline {
    agent any
    
    parameters {
        booleanParam(name: 'flag', defaultValue: true, description: 'Set flag to true or false')
        string(name: 'VERSION', defaultValue: '2.2.4', description: 'Specify the version')
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building... with version ${params.VERSION}"
                    // Add your build commands here
                }
            }
        }

        stage('Test') {
            when {
                expression {
                    return params.flag == false
                }
            }
            steps {
                echo 'Testing...'
                // Add your test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying... And test stage should be skipped'
                // Add your deployment commands here
            }
        }
    }

    post {
        always {
            echo 'This will always run, regardless of the build result'
            // Add any post-build actions that should always run here
        }
        failure {
            echo 'This will run only if the build fails'
            // Add any post-build actions specific to failure here
        }
    }
}
