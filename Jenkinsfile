
pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK21'
    }

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Ranjeet0829/ecommerce-devops-project.git'
            }
        }

        stage('Maven Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t ecommerce-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker run -d --name ecommerce-container -p 8080:8080 ecommerce-app'
            }
        }
    }
}
