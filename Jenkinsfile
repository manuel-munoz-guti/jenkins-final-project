pipeline {
    agent none

    stages{   
        stage('Clone Backend Repository for DEV environment') {
            agent { label 'debian-test' }
            steps {
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
                echo 'Cloned Backend Project'
            }
        }
        stage('Build backend for DEV with docker-compose') {
            agent { label 'debian-test' }
            steps {
                sh 'docker-compose up -d'
                echo 'Build DEV backend'
            }
        }
        stage('Clone Frontend Repository for DEV environment') {
            agent { label 'debian-test' }
            steps {
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
                echo 'Cloned Frontend Project'
            }
        }
        stage('Build frontend for DEV with docker-compose') {
            agent {label 'debian-test'}
            steps {
                sh 'docker-compose up -d dev'
                echo 'Build DEV frontend'
            }
        }
        stage('Clone Frontend Repository for QA environment') {
            agent { label 'master' }
            steps {
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
                echo 'Cloned Frontend Project'
            }
        }
        stage("Run Automation tests in Dockerfile.test QA"){
            agent { label 'master' }
            steps {
                sh 'docker-compose up -d test'
                echo 'Build tests passes'
            }
        }
        stage('Clone Backend Repository for PROD environment') {
            agent { label 'debian_server' }
            steps {
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
                echo 'Cloned Backend Project'
            }
        }
        stage('Build backend for PROD with docker-compose') {
            agent { label 'debian_server' }
            steps {
                sh 'docker-compose up -d'
                echo 'Build PROD backend'
            }
        }
        stage('Clone Frontend Repository for PROD environment') {
            agent { label 'debian_server' }
            steps {
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
                echo 'Cloned Frontend Project'
            }
        }
        stage('Build frontend for PROD with docker-compose') {
            agent {label 'debian_server'}
            steps {
                sh 'docker-compose up -d hero-webapp'
                echo 'Build PROD frontend'
            }
        }
    }
}