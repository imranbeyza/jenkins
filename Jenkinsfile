pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'imran-html-server'
        CONTAINER_NAME = 'imran'
        PORT_MAPPING = '4444:80'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image(env.DOCKER_IMAGE).run("-d --name ${env.CONTAINER_NAME} -p ${env.PORT_MAPPING}")
                }
            }
        }
