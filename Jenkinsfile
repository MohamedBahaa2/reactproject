pipeline{
    agent{
        label 'docker'
    }
    stages {
        stage('Build Docker Image'){
            script{
                sh 'docker build -t mohamedbahaa2/docker-react -f Dockerfile.dev .'
            }
        }
        stage('Run Tests'){
            script{
                env.DOCKER_BUILDKIT = 1
                sh 'docker run -e CI=true mohamedbahaa2/docker-react npm test'
            }
        }
    }
}