pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                bat 'git clone https://github.com/priya1626/mdp_isa_2327.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t mdp_isa2_2327 .'
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
                bat 'docker run -d --name priya_2327 mdp_isa2_2327'
            }
        }
    }
}
