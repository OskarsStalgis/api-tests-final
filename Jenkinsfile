pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build') {
            steps {
                buildApp()
            }
        }
    }
}

def buildApp(){
    echo "Building of node application is starting.."
    sh "docker build -t oskarsstalgis/api-tests:latest ."

    echo "Pushing img to Docker registry.."
    sh "docker push oskarsstalgis/api-tests:latest"
}
