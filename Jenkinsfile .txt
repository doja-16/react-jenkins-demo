pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/doja-16/react-jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging the project...'
                bat 'echo Demo package created successfully'
            }
        }
    }
}
