pipeline {
    agent any

    stages {

        stage('Checkout apache-commons-io') {
            steps {
                echo 'Checkout Project'
                dir ('apache-commons-io') {
                checkout([$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/apache/commons-io.git']], branches: [[name: '*/master']]])

sh "ls -lart ./*"
                }

            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}