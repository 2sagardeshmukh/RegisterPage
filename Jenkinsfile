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
                artifactId: 'torryharris',
                classifier: '',
                file: '/var/lib/jenkins/jobs/register/config.xml', 
                type: 'war'
            ]
        ], 
            credentialsId: '73497722-8b4b-46b2-99d2-cf525eb9978e',
            groupId: 'torryharris', 
            nexusUrl: '18.118.247.213:8081', 
            nexusVersion: 'nexus3',
            protocol: 'http', 
            repository: 'maven-snapshots', 
            version: '1.0-SNAPSHOT'
           }
       }
    }
}
