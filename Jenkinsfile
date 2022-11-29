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
                echo 'Clonning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Docker Build Backend') {
            steps {
                sh 'docker build -t jsonserver .'
            }
        }
        stage('Docker Build FrontEnd') {
            steps {
                sh 'docker build -t jsonserver .'
            }
        }
        stage('Cloning Docker Compose Fullstack Repository') {
            steps {
                echo 'Clonning Composer repository'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/laboratorio4.git'
            }
        }
        stage('Build Backend and Frontend') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}