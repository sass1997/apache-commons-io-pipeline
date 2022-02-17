pipeline {
    /*
    Installed Plugins
    Maven IntegrationVersion 3.17
    */
    agent any
    tools {
        maven 'maven-3.8.4' 
        jdk 'java-9' 
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
                    sh "export MAVEN_HOME=/opt/maven"
                    sh "export PATH=$PATH:$MAVEN_HOME/bin"
                    sh "mvn --version"
                    
                    
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