pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: env.BRANCH_NAME, credentialsId: 'github-credentials', url: 'https://github.com/YefriGonzalez/react-front.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Run') {
            steps {
                sh 'npm start &'
            }
        }
    }

    post {
        success {
            echo 'Frontend desplegado correctamente en local'
        }
        failure {
            echo 'Error en el pipeline'
        }
    }
