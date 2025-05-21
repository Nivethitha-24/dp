pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/Nivethitha-24/dp.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step required for static HTML.'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Ensure the user running Jenkins has sudo permissions (without password) for this command
                    sh 'sudo cp -r * /var/www/html/'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
