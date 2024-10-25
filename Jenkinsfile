pipeline {
    agent any

    environment {
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                git url: 'https://github.com/priya1626/MDP_ISA_2327.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                script {
                    bat 'docker build -t MDP_ISA2_2327 .'
                }
            }
        }
        stage('Verify Docker Image') {
          steps {
            bat 'docker images'
          }
      }
        stage('Login to Docker Hub') {
          steps {
            bat 'docker login -u "priyamvada1626" -p "Varsha1626@" docker.io' 
          }
      }

        stage('Run Container in doemon mode') {
            steps {
                echo 'Running container...'
                script {
                    bat 'docker run -d --name priya_2327 MDP_ISA2_2327'
                }
            }
        }
    }
}
