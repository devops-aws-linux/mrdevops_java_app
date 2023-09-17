@Library('my-shared-library') _
pipeline{
    agent any
    stages{
        stage('message'){
            steps{
                checkout(
                    branch: "main",
                    url: "https://github.com/devops-aws-linux/mrdevops_java_app.git"
                )
            }
        }
    }
}