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
                            artifactId: 'sparkjava-hello-world', 
                            classifier: '', 
                            file: "target/webapp.war", 
                            type: 'war'
                        ]
                    ], 
                    credentialsId: 'b4408069-1499-44ba-97ab-fd84e2998697',
                    groupId: 'sparkjava-hello-world', 
                    nexusUrl: '172.31.46.232:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'simple-app', 
                    version: '1.0.0'
                    
            }
        }
    }
}
