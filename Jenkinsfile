pipeline {
    agent any

    stages {
dir ('apache-commons-io') {
        stage('Checkout apache-commons-io') {
            steps {
                echo 'Checkout Project'
                
                checkout([$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/apache/commons-io.git']], branches: [[name: '*/master']]])
                

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
}