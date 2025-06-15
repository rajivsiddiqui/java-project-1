pipeline {
    agent any

    stages {
        stage('git_clone') {
            steps {
                git branch: 'main', url: 'https://github.com/rajivsiddiqui/java-project-1.git'
            }
        }
        //build stage 
        stage('build') {
            steps {
                sh 'mvn clean deploy' //-Dmaven.test.skip=true
            }
        }
    }
}
