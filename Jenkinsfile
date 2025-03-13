pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '**/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/monish-suresh/PES1UG22CS361_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS361-1 main.cpp || exit 1'  // Compilation will fail if there's an error
                sh 'exit 1'  // Force failure
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22CS361-1'  // This won't execute if Build fails
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed at the Build stage!"  // Log failure in post actions
        }
    }
}
