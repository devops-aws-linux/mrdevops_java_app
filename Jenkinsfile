@Library('java_shared') _
pipeline{
    agent any
    tools {
        maven 'maven3'
        jdk 'java11'
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose Create/Destroy')
    }
    
    stages{
        when { expression {param.action == 'create'} }
        stage("SCM Checkout"){
            steps{
                gitCheck(
                     branch: 'main',
                     url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
                )
            }
        }
        stage('OWASP Dependency-Check Vulnerabilities') {
            when { expression {param.action == 'create'} }
            steps {
                dependencyCheck additionalArguments: ''' 
                -o './'
                -s './'
                -f 'ALL' 
                --prettyPrint''', odcInstallation: 'DPC'
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
        }
        stage('Maven Compile'){
            when { expression {param.action == 'create'} }
            steps{
               script{
                mavenCompile()
               }
            }
        }
        stage('Maven Integration Test'){
            when { expression {param.action == 'create'} }
            steps{
                script{
                    mavenIntegration()
                }
            }

        }
        stage('Maven Test'){
            when { expression {param.action == 'create'} }
            steps{
                script{
                    mavenTest()
                }
            }
        }
    }
}