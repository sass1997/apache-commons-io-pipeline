pipeline {
    agent any

    stages {

        stage('Checkout apache-commons-io') {
            steps {
                echo 'Checkout Project'
                checkout([$class: 'MercurialSCM', source: 'https://github.com/apache/commons-io.git', branch: 'main'])



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