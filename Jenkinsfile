pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/sumanasm360-dev/MyMavenSeleniumApp02.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Login Test') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass=com.example.App'
            }
        }
    }

    post {
        success {
            echo 'Selenium CI/CD Successful!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}
