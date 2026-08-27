pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:${env.PATH}"
    }

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

                // Remove old container if it exists
                sh "docker rm -f mycontainer || exit(0)"

                // Run the new container
                sh "docker run -d --name mycontainer -p 5001:5000 mypythonflaskapp"
            }
        }
    }
}
