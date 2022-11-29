pipeline {
    agent none

    stages{   
        stage('Clone Repository for DEV environment') {
            agent { label 'debian-test' }
            steps {
                echo 'Cloning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
                echo 'Cloning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Build for DEV with docker-compose') {
            agent {label 'debian-test'}
            steps {
                sh 'docker-compose up -d dev'
                echo 'Build DEV backend'
                sh 'docker-compose up -d hero-webapp'
                echo 'Build DEV frontend'
            }
        }
    }
}