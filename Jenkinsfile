@Library('ullagallu') _

pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            steps {
               checkout(
                    branch: 'main',
                    url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
               ) 
            }
        }
    }
}
