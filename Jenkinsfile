pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Validate Files') {
            steps {
                sh '''
                    set -eu
                    test -f index.html
                    test -f style.css
                    echo "Website files verified successfully"
                '''
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                    set -eu

                    mkdir -p /deploy
                    cp index.html style.css /deploy/

                    echo "Website deployed to Apache shared volume"
                '''
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: DevLaunch deployed successfully!'
        }

        failure {
            echo 'FAILED: Check the Console Output for errors.'
        }
    }
}
