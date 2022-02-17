pipeline {
    /*
    Installed Plugins
    Maven Integration - Version 3.17
    Pipeline Maven Integration - Version:
    */
    agent any
    tools {
        maven "maven-3.8.4" 
        jdk "jdk9"
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
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
                
                

sh "ls -la /var/jenkins_home/tools/hudson.tasks.Maven_MavenInstallation/maven-3.8.4/bin"
                sh "/var/jenkins_home/tools/hudson.tasks.Maven_MavenInstallation/maven-3.8.4/bin --version"           
                    
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