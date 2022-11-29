pipeline {
    agent none

    stages {
        stage('Deploying for dev Environment') {
            agent {label 'debian-test'}
            steps {
                echo 'Clonning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
                echo 'Building dev backend'
                sh 'docker compose up -d'
                echo 'Clonning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
                echo 'Building dev frontend'
                sh 'docker-compose up -d dev'
            }
        }
        stage('Deploying for production Environment') {
            agent {label 'debian_server'}
            steps {
                echo 'Clonning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
                echo 'Building dev backend'
                sh 'docker compose up -d'
                echo 'Clonning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
                echo 'Building dev frontend'
                sh 'docker-compose up -d hero-webapp'
            }
        }
    }
}