pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/SILENTWRAlTH/PES2UG21CS401_jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                build 'PES2UG21CS401-1'
                sh 'g++ main.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
            post {
                failure {
                    error 'Pipeline failed'
                
            
        }
    }
}
