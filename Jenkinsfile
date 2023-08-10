pipeline {
    agent any
    tools {
        maven "maven"
    }
    stages {
        stage('clone repo and clean ') {
            steps {
               sh "rm -rf mavenproject"
               sh "git clone -b master https://github.com/amar-prime/mavenproject.git" 
               sh "mvn clean -f mavenproject"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test -f mavenproject" 
            }
        }
        stage('Deploy') {
            steps {
                sh "mvn package -f mavenproject"
            }
        }
    }
}
