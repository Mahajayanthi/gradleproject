pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/Mahajayanthi/gradleproject.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'gradle clean build -p gradleproject'
            }
        }
        
        stage('Test') {
            steps {
                sh 'gradle test -p gradleproject'
            }
        }
        
        stage('Package') {
            steps {
                sh 'gradle assemble -p gradleproject'
            }
        }
    }
}
