pipeline {
    agent any

    tools {
        maven 'Maven'   
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/JenkinsSrvAcc/Jenkins', credentialsId: 'git'
            }
        }
        stage('Build with Maven') {
            steps {
                script {
                    if (fileExists('pom.xml')) {
                        echo 'Building with Maven...'
                        sh 'mvn clean install'
                    }
                }
            }
        }
               stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test commands here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment steps here
            }
        }
    }
}