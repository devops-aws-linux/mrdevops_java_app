pipeline{
    agent any
    tools{
        maven 'maven3'
    }
    stages{
        stage("Maven test"){
            steps{
                 sh 'mvn --version' 
            }
        }
    }
}
