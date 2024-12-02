pipeline {
    agent any
    environment {
        GIT_REPO = 'https://github.com/SamathaMaram/jenkins.git'
        GIT_BRANCH = 'main'
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the repository...'
                git branch: "${env.GIT_BRANCH}", 
                    url: "${env.GIT_REPO}"
            }
        }
        stage('Set Permissions') {
            steps {
                echo 'Setting executable permissions for test.sh...'
                sh 'chmod +x ./test.sh'
            }
        }
        stage('Run Shell Script') {
            steps {
                echo 'Running the shell script...'
                sh './test.sh'
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution completed!'
        }
    }
}
