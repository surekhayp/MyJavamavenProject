
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
       

         stage('Deploy')
        {
            steps{ echo " job  executed successfully..............!!!"}
        }
         stage('Deliver') {
            steps {
                bat './jenkins/scripts/deliver.bat'
            }
        }
    }
}
