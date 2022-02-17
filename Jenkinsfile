pipeline {
    /*
    Installed Plugins
    Maven Integration - Version 3.17
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
                echo 'Build'
                dir ('apache-commons-io') { 
                    sh "mvn clean package -DskipTests=true"                    
                }

            }
        }
        stage("Benchmark") {
            steps {
                echo "Run Profile Benchmark"
                 dir ('apache-commons-io') { 
                    sh "mvn clean package -P benchmark"                    
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Tests'
                dir ('apache-commons-io') { 
                    sh "mvn test"
                }
            }
        }
        // Additional Possible Stage to Upload Code and Test Result to SonarQube
        // Pre Requisite would be to have a SonarQube Instance Running
        stage('Quality') {
            steps {
                echo 'Run Sonar'
                dir ('apache-commons-io') { 
                    sh 'mvn sonar:sonar'
                }
            }
        }

        // Additional Possible Stage if you would like to deploy your builded maven artefacts to upstream e.x https://repo.maven.apache.org
        // Project has already defined a Release Profile to do prepare the versions in pom.xml
        stage('Deploy') {
            steps {
                echo 'Deploy'
                dir ('apache-commons-io') { 
                    sh "mvn package -P release"
                    sh "mvn deploy"
                }
            }
        }
    }
}
