pipeline {
    agent any
    tools {
        maven 'Maven'   // Replace with your configured Maven name
        jdk 'JDK'          // Replace with your configured JDK name
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/R-Navyashree/MyApp02.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Run Application') {
            steps {
                sh 'java -cp target/MyApp02-1.0-SNAPSHOT.jar com.example.App'
            }
        }
    }
    post {
        success {
            echo 'Build and Deployment Successful'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
