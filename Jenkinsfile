pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: '26597cc1-480d-45d0-bc20-63bdd039dba6', url: 'https://github.com/SharanyaJayaram/Hotel-Management-System.git']]])
            }
        }
        stage('Build and Test') {
            steps {
                sh ''' ls -lart
                mvn clean install '''
            
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Scanned successfully!"
            }
        }
        stage('Notification') {
            steps {
                emailext body: 'Build was successful, Thank you!', subject: 'Build Status', to: 'gauravbarua008@gmail.com'
            }
        }
        }
    }
}
