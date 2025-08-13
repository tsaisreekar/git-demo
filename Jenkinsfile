pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/tsaisreekar/git-demo.git'
            }
        }
        stage('Build with Maven') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Archive Artifact'){
            steps{
                archiveArtifacts artifacts:'target/*.jar', fingerprint:true
            }
        }
    }
}
