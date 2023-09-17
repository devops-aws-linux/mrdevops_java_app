pipeline{
    agent any
    stages{
        stage('SCM Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
            }
        }
    }
}