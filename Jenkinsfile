pipeline {
    agent any

    stages('Building for DEV environment') {    
        stage('Cloning for DEV') {
            agent {label 'debian-test'}
            steps {
                echo 'Cloning Backend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
            }
            steps {
                echo 'Cloning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Build for DEV with docker-compose') {
            agent {label 'debian-test'}
            steps {
                sh 'docker-compose up -d dev'
            }
            steps {
                sh 'docker-compose up -d hero-webapp'
            }
        }
    }
}