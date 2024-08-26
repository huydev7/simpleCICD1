pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                script {
                    // Cài đặt các phụ thuộc
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Thực hiện kiểm tra (nếu có)
                    // sh 'npm test'
                    echo 'No tests implemented yet.'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Triển khai ứng dụng
                    echo 'Deploying application...'
                }
            }
        }
    }
}
