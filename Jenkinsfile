pipeline{
    agent any
    tool{
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
