pipeline {
    agent {
        docker {
            image 'node:16' // Sử dụng image Node.js
            args '-u root' // Chạy với quyền root
        }
    }

    stages {
        stage('Install Docker') {
            steps {
                script {
                    // Cài đặt Docker
                    sh '''
                        apt-get update
                        apt-get install -y \
                        apt-transport-https \
                        ca-certificates \
                        curl \
                        software-properties-common

                        # Thêm khóa GPG cho Docker
                        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -

                        # Thêm repository Docker vào APT
                        add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

                        # Cài đặt Docker
                        apt-get update
                        apt-get install -y docker-ce
                    '''
                }
            }
        }

        stage('Install Node.js') {
            steps {
                script {
                    // Cài đặt Node.js nếu cần
                    sh '''
                        curl -sL https://deb.nodesource.com/setup_16.x | bash -
                        apt-get install -y nodejs
                    '''
                }
            }
        }

        stage('Install npm Packages') {
            steps {
                // Chạy npm install
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Chạy các lệnh build nếu cần
                sh 'npm run build'
            }
        }

        // Thêm các stage khác nếu cần
    }
}
