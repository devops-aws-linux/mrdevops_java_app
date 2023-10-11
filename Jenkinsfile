pipeline{
    agent any
    tools {
        maven 'maven3'
        jdk 'java17'
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }
    
    stages{
        stage("SCM Checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
            }
        }
        stage('Maven Compile'){
            steps{
                sh 'mvn clean compile'
            }
        }
    }
}