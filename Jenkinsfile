pipeline{
    agent any
    tools{
        maven 'maven3'
    }
    stages{
        stage("Maven Clean"){
            steps{
                 sh 'mvn clean install package -DskipTests' 
            }
        }
    }
}
