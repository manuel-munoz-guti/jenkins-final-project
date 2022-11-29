pipeline {
    agent {label 'debian_server'}

    stages {
        stage('Cloning Back end') {
            steps {
                echo 'Clonning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
            }
        }
        stage('Cloning Front end') {
            steps {
                echo 'Clonning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Prepare Docker Image Backend') {
            steps {
                sh 'docker build -t jsonserver .'
            }
        }
        stage('Prepare Docker Image FrontEnd') {
            steps {
                sh 'docker build -t diplomado/heroes-app .'
            }
        }
        stage('Cloning Fullstack Repository') {
            steps {
                echo 'Clonning Composer repository'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/laboratorio4.git'
            }
        }
        stage('Build Fullstack repository') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}