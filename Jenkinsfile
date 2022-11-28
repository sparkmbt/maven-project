pipeline{
    tools{
        jdk 'java8'
        maven 'maven'
    }
    agent any
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/edureka-git/DevOpsClassCodes.git'
            }
        }
        stage('compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('codeReview'){
            steps{
                sh 'mvn -P metrics pmd:pmd'
            }
        }
        stage('unitTest'){
            steps{
                sh 'mvn test'
            }
        }
        stage('metricCheck'){
            steps{
                sh 'mvn cobertura:cobertura'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
            
        }

    }
}
