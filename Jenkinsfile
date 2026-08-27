pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:$PATH"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build Docker Image'
                sh 'docker build -t devops .'
            }
        }

        stage('Run') {
            steps {
                echo 'Run Docker Container'
                sh 'docker run -d -p 5001:5000 devops'
            }
        }
    }
}