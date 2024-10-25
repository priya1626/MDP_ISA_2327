pipeline {
    agent any

    environment {
        IMAGE_NAME = "MDP_ISA2_2327"
        CONTAINER_NAME = "2327"
        REPO_URL = 'https://github.com/priya1626/MDP_ISA_2327.git'
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                git url: "${REPO_URL}"
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                script {
                    bat "docker build -t ${IMAGE_NAME} ."
                }
            }
        }
        stage('Verify Docker Image') {
          steps {
            bat "docker images"
          }
      }
        stage('Login to Docker Hub') {
          steps {
            bat 'docker login -u "priyamvada1626" -p "Varsha1626@" docker.io' }
      }

        stage('Run Container') {
            steps {
                echo 'Running new container...'
                script {
                    bat "docker run -d --name ${CONTAINER_NAME} ${IMAGE_NAME}"
                }
            }
        }
    }
