pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/rmodi2605/jenkins_pipeline_for_Petclinic_App.git'
            }
        }
        
        /*stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv(credentialsId: 'sonar_secret') {
                    sh 'mvn clean package sonar:sonar'  
                }
            }
        }*/
    
        stage('Docker Build') {
            steps {
                sh 'docker build -t petclinic-app . -f Dockerfile'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
