@Library('my-shared-library') _

pipeline{
    agent any
    stages{
        stage("SCM Checkout"){
            steps{
                checkout(
                    branch: "main",
                    url: "https://github.com/devops-aws-linux/mrdevops_java_app.git"
                )
            }
        }
    }
}