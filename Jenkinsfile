pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                    always {
                        junit 'Test*.xml'
                    }
            }
        }
        stage('Deliver') {
            steps {
                // sh './jenkins/scripts/deliver.sh'
                echo 'Delivered'
            }
        }
    }
}
