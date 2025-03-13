pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'ls -la main'  // List files inside 'main' to verify hello.cpp exists
                sh 'g++ -o main/hello_exec main/hello.cpp'  // Compile hello.cpp from 'main' folder
            }
        }
        stage('Test') {
            steps {
                sh 'chmod +x main/hello_exec'  // Make the executable file runnable
                sh './main/hello_exec'  // Run the compiled program
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
