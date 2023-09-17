@Library('my-shared-library') _

pipeline{
    agent any
    stages{
        stage("Hello World"){
            steps{
               scmCheckout(
                branch: 'main',
                url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
               )
            }
        }
    }
}
