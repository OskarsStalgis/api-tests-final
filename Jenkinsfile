pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build') {
            steps {
                buildImapge()
            }
        }
    }
}

def buildImage(){
    echo "Building of Docker Image is starting.."
    sh "docker build -t oskarsstalgis/api-tests:latest ."

    echo "Pushing image to Docker registry.."
    sh "docker push oskarsstalgis/api-tests:latest"
}
