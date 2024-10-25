pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                bat 'git clone https://github.com/priya1626/MDP_ISA_2327.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t MDP_ISA2_2327 .'
            }
        }
        stage('Verify Docker Image') {
          steps {
            bat 'docker images'
          }
      }
        stage('delete'){
            steps{
                bat 'docker rm -f priya_2327'
            }
        }

        stage('Run Container in doemon mode') {
            steps {
                echo 'Running container...'
                bat 'docker run -d --name priya_2327 MDP_ISA2_2327'
            }
        }
    }
}
