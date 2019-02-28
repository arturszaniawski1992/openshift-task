pipeline {
    agent any 

    stages {
        stage('Build') { 
            steps { 
                sh 'sleep 5' 
            }
        }
        stage('Test'){
            steps {
                sh 'sleep 5'
               
            }
        }
        stage('Deploy') {
            steps {
                sh 'sleep 5'
            }
        }
		
		
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
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
    
}