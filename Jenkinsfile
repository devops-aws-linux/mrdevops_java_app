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
    
    stages{
        stage("SCM Checkout"){
            steps{
                gitCheck(
                     branch: 'main',
                     url: 'https://github.com/devops-aws-linux/mrdevops_java_app.git'
                )
            }
        }
        stage('OWASP Dependency-Check Vulnerabilities') {
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
            steps{
               script{
                mavenCompile()
               }
            }
        }
        stage('Maven Integration Test'){
            steps{
                script{
                    mavenIntegration()
                }
            }

        }
        stage('Maven Test'){
            steps{
                script{
                    mavenTest()
                }
            }
        }
    }
}