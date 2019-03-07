pipeline {
    agent any 
    stages {
        stage('Checkout') { 
            steps {
                // Checkout from Githubn
                 checkout([$class: 'GitSCM', branches: [[name: 'Feb4_1']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '168ebbe6-8ab2-408d-89b4-4973ab535f14', url: 'https://github.com/ivishalsinghal/SQTrng.git']]])  
  

            }
        }
        stage('Build') { 
            steps {
                // Maven Build
                bat 'mvn clean install'
  

            }
        }
        stage('SQ Analysis') { 
            steps {
                // SQ Analyzer
                bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
 
 
            }
        }
    }
}
