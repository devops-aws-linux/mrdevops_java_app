pipeline{
    agent any
    tools{
        maven 'maven3'
    }
    stages{
        stage("Maven Clean"){
            steps{
                 sh 'mvn clean' 
            }
        }
        stage("Maven Compile"){
            steps{
                 sh 'mvn compile' 
            }
        }
        stage("Maven test"){
            steps{
                 sh 'mvn test' 
            }
        }
        stage("Maven Build"){
            steps{
                 sh 'mvn package' 
            }
        }
    }
}
