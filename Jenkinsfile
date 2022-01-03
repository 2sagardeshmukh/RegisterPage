pipeline {
    agent any
    tools {
         maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                  sh script: 'mvn clean package'
            }
        }
       stage('Upload War To Nexus'){
            
           steps{
        
        nexusArtifactUploader artifacts: [
            [
                artifactId: 'th',
                classifier: '',
                file: '/var/lib/jenkins/jobs/registerdemo/config.xml', 
                type: 'war'
            ]
        ], 
            credentialsId: '73497722-8b4b-46b2-99d2-cf525eb9978e',
            groupId: 'th', 
            nexusUrl: '3.133.254.46:8081', 
            nexusVersion: 'nexus3',
            protocol: 'http', 
            repository: 'maven-snapshots', 
            version: '1.0-SNAPSHOT'
           }
       }
    }
}
