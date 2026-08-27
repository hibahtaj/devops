pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build Docker Image"
                sh "docker build -t mypythonflaskapp ."
            }
        }

        stage('Run') {
            steps {
                echo "Run application in Docker Container"

                sh "docker rm -f mycontainer || true"

                sh "docker run -d --name mycontainer -p 5001:5000 mypythonflaskapp"
            }
        }
    }
}