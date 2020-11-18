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
    }
}
