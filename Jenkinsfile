pipeline {
    # Installed Plugins
    # 	Maven IntegrationVersion 3.17
    agent any
    tools {
        maven 'maven-3.8.4' 
    }
    stages {

        stage('Checkout apache-commons-io') {
            steps {
                echo 'Checkout Project'
                dir ('apache-commons-io') {
                    checkout([$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/apache/commons-io.git']], branches: [[name: '*/master']]])
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
                dir ('apache-commons-io') {
                    sh "maven clean package"
                }

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