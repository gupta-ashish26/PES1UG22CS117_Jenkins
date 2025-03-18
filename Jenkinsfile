pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    userRemoteConfigs: [[url: 'https://github.com/gupta-ashish26/PES1UG22CS117_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS117-1'
                sh 'g++ ./main/hello.cpp -o ./output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stageeee('Deploy') {
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
