pipeline {
    agent {
        node {
            label 'slave1'
        }
    }

   stages {
        stage('Build') {
            steps {
                sh '''
                    sudo yum update -y
                    sudo yum install httpd -y
                    sudo systemctl start httpd
                    sudo systemctl enable httpd
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    sudo cp -R . /var/www/html/
                '''
            }
        }
    }

}
