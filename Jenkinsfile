pipeline {
    agent any

    parameters {
        string(name: 'DOCKER_IMAGE_VERSION', defaultValue: '', description: 'Docker Image Version')
    }

    stages {
        stage('update deploy.yaml') {
            steps {
                // Jenkins 파이프라인에서 작업 디렉터리를 변경할 때 사용한다.
                dir('department-api') {
                    sh 'pwd'
                    sh 'ls -al'
                    echo "Received Docker Image Version : ${params.DOCKER_IMAGE_VERSION}"
                    sh 'git checkout main'
                    sh "sed -i 's|alskung/department-service:.*|alskung/department-service:${params.DOCKER_IMAGE_VERSION}|g' deploy.yaml"
                    sh 'cat deploy.yaml'
                }
            }
        }

        stage('Commit & Push') {
            steps {
                sh 'git status'
                sh 'git config --list'
                sh 'git config user.name "jenkins"'
                sh 'git config user.email "jenkins@beyond.com"'
                sh 'git config --list'
                sh 'git config --list'
            }
        }
    }
}