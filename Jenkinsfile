pipeline{
    agent any
    tools {
        maven 'maven-builder'
    }
    stages{
        stage('Build'){
            steps{
                 sh 'mvn clean package'
            }
        }
        stage('Upload War file to Nexus'){
            steps{
                 nexusArtifactUploader artifacts: [
                     [
                         artifactId: 'simple-app', 
                         classifier: '', 
                         file: 'target/simple-app-3.0.0.war', 
                         type: 'war'
                     ]
                ], 
                credentialsId: 'Nexus3', 
                groupId: 'in.javahome', 
                nexusUrl: '172.31.34.55:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'simple-app-release', 
                version: '3.0.0'
            }
        }
    }
}
