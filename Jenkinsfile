pipeline {
    agent any
    stages('Building for DEV environment') {
        agent {label 'debian-test'}
        stage('Cloning Backend for DEV') {
            steps {
                echo 'Cloning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
            }
        }
        stage('Cloning Frontend for DEV') {
            steps {
                echo 'Clonning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Build backend DEV with docker-compose') {
            steps {
                sh 'docker-compose up -d dev'
            }
        }
        stage('Build frontend DEV with docker-compose') {
            steps {
                sh 'docker-compose up -d hero-webapp'
            }
        }
    }
}