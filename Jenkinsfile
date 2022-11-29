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
                echo 'Clonning Frontend Project'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
            }
        }
        stage('Docker Build Backend') {
        stage('Prepare Docker Image Backend') {
            steps {
                sh 'docker build -t jsonserver .'
            }
        }
        stage('Docker Build FrontEnd') {
        stage('Prepare Docker Image FrontEnd') {
            steps {
                sh 'docker build -t jsonserver .'
                sh 'docker build -t diplomado/heroes-app .'
            }
        }
        stage('Cloning Docker Compose Fullstack Repository') {
        stage('Cloning Fullstack Repository') {
            steps {
                echo 'Clonning Composer repository'
                git branch: 'main', url: 'https://github.com/manuel-munoz-guti/laboratorio4.git'
            }
        }
        stage('Build Backend and Frontend') {
        stage('Build Fullstack repository') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}
// pipeline {
//     agent none

//     stages {
//         stage('Deploying for dev Environment') {
//             agent {label 'debian-test'}
//             steps {
//                 echo 'Clonning Backend Project'
//                 git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
//                 echo 'Building dev backend'
//                 sh 'docker compose up -d'
//                 echo 'Clonning Frontend Project'
//                 git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
//                 echo 'Building dev frontend'
//                 sh 'docker-compose up -d dev'
//             }
//         }
//         stage('Deploying for production Environment') {
//             agent {label 'debian_server'}
//             steps {
//                 echo 'Clonning Backend Project'
//                 git branch: 'main', url: 'https://github.com/manuel-munoz-guti/backend-vue.git'
//                 echo 'Building dev backend'
//                 sh 'docker compose up -d'
//                 echo 'Clonning Frontend Project'
//                 git branch: 'main', url: 'https://github.com/manuel-munoz-guti/projecto-vue.git'
//                 echo 'Building dev frontend'
//                 sh 'docker-compose up -d hero-webapp'
//             }
//         }
//     }
// }