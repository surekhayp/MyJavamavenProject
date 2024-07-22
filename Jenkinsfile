
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                 #'mvn -B -DskipTests clean package'
                mvn clean
            }
        }
        stage('Test') {
            steps {
                 'mvn test'
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
