pipeline {
    agent{ label 'master'}
    tools {maven 'm3'}
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: "https://github.com/stas112/SpringPetClinic.git"
            }
        }
        stage('build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/petclinicdeclaratedpipeline/target/*.jar'
            }
        }
    }
}