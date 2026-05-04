pipeline {
    agent any

    parameters {
        string(name: 'DOCKER_IMAGE_VERSION', defaultValue: '', description: 'Docker Imagae Version')
    }
    stages {
        stage('Hello') {
            steps {
                sh 'pwd'
                sh 'ls -al'
                echo "${DOCKER_IMAGE_VERSION}"
            }
        }
    }
}
