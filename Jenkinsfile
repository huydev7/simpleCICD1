pipeline {
    agent any 

    stages {
        stage('Install Node.js') {
            steps {
                script {
                    // Cài đặt Node.js và npm (không sử dụng sudo)
                    sh '''
                        curl -sL https://deb.nodesource.com/setup_16.x | bash -
                        apt-get install -y nodejs
                    '''
                }
            }
        }

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
