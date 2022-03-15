pipeline {
    agent any
    stages {
        stage('Test Maven install') {
            steps {
                sh "export MAVEN_HOME=/opt/maven"
                sh "export PATH=$PATH:$MAVEN_HOME/bin"
                sh "mvn --version"
            }
        }
        stage('Build') {
            steps {
                sh "mvn compile"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
            post {
                always {
                    junit '**/TEST*.xml'
                }
            }
        }
    }
}