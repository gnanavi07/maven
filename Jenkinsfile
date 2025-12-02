pipeline {
    agent any

    tools {
        maven 'Maven-3.9'
        jdk 'JDK-21'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/YOUR_USERNAME/jenkins-maven-demo.git'
            }
        }

        stage('Build with Maven') {
            steps {
                bat "mvn clean package"   // if Jenkins on Windows
                // sh "mvn clean package" // if Jenkins on Linux
            }
        }

        stage('Archive JAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
