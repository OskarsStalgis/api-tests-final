pipeline {
    agent any
    environment{
        DOCKER_USR='oskarsstalgis'
    }
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build') {
            steps {
                buildDockerImg()
            }
        }
    }
}

def buildDockerImg(){
    echo "Building of Docker Image is starting.."
    sh "docker build -t ${DOCKER_USR}/api-tests:latest ."

    echo "Pushing image to Docker registry.."
    sh "docker push ${DOCKER_USR}/api-tests:latest"
}
