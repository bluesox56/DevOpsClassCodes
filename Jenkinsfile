pipeline {
    agent any

    tools {
        jdk 'myjava'
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mymaven"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
            }
        }    
    stage('Compile') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn compile'
            }
        }  
    stage('codereview') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn pmd:pmd'
            }
        }    
    stage('UnitTest') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn test'
            }
        }    
     stage('MetricCheck') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }  
     stage('Package') {
            steps {
                // Get some code from a GitHub repository
                sh 'mvn package'
            }
        }       
        
    }
}
