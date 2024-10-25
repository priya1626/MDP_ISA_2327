pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
                echo 'Copying...'
                bat 'copy "C:\\Users\\OneDrive\\Desktop\\2327_MDP_ISA2" "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Pipeline_ISA2_2327"'
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

        stage('Delete Old Container') {
            steps {
                bat 'docker rm -f priya_2327 || echo "No existing container to remove"'
            }
        }

        stage('Run Container in Daemon Mode') {
            steps {
                echo 'Running container...'
                bat 'docker run -d --name priya_2327 mdp_isa2_2327'
            }
        }
    }
}

