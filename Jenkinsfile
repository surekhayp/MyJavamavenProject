
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bash 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bash 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                bash './jenkins/scripts/deliver.sh'
            }
        }
    }
}
