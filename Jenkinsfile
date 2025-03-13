pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'ls -la'  // List files to check if hello.cpp exists
                sh 'g++ -o hello_exec hello.cpp'  // Compile hello.cpp
            }
        }
        stage('Test') {
            steps {
                sh 'chmod +x hello_exec'  // Ensure it's executable
                sh './hello_exec'  // Run the compiled program
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful!'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
