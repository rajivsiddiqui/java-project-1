pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
        DOCKERHUB_CREDENTIALS = credentials('docker-hub-credential')

    } 
    stages {
        stage('git_clone') {
            steps {
                git branch: 'main', url: 'https://github.com/rajivsiddiqui/java-project-1.git'
            }
        }
        //build stage 
        stage('build') {
            steps {
                //sh 'mvn clean deploy -Dmaven.test.skip=true'  //-Dmaven.test.skip=true
                sh 'mvn clean install'
            }
        }
        //docker image create
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devopssteps/java-1:latest .'
            }
        }
    }
}
