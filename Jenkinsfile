pipeline {
agent {
    docker {
        image 'grapeupci/ubuntu-kubectl:1.0.0'
    }
}
    options {
        buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '3', numToKeepStr: '3'))
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'HOURS')
        timestamps() // Corrected syntax here
    }

    stages {
        stage('Test') {
            steps {
                sh '''
                kubectl 
                pwd
                uname -r 
                touch mamadou
                '''
            }
        }

        stage('Validate') {
            steps {
                sh 'pwd'
            }
        }

        stage('Scan') {
            steps {
                sh 'pwd'
            }
        }

        stage('Build') {
            steps {
                sh '''
                echo "FROM httpd:2.4" > Dockerfile
                docker build -t mamadou .
                docker images
                '''
            }
        }

        stage('Push') {
            steps {
                sh 'pwd'
            }
        }

        stage('Deploy') {
            steps {
                sh 'pwd'
            }
        }
    }
}
