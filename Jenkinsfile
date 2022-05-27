pipeline {
    agent any

    stages {
        stage('cloning repository') {
            steps {
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }

        stage('creating war') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploying to tomcat') {
            steps {
            deploy adapters: [tomcat9(credentialsId: '56381e23-12e2-42a8-afff-adf637c55aa7', path: '', url: 'http://18.212.16.99:8080/')], contextPath: 'game', war: '**/*.war'    
            }
        }
    }
}
