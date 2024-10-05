pipeline {
    agent any
    stages {
        stage('Checkout the code from GitHub') {
            steps {
                git url: 'https://github.com/Ashadow9/Staragile-Banking-and-Finance-Domain-Project/'
                echo 'GitHub URL checked out'
            }
        }
        stage('Code compile with Maven') {
            steps {
                echo 'Starting compilation'
                sh 'mvn compile'
            }
        }
        stage('Code testing with Maven') {
            steps {
                echo 'Running unit tests'
                sh 'mvn test'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                echo 'Running Selenium tests'
                sh 'mvn test -Dtest=YourSeleniumTestClassName' // Adjust the class name accordingly
            }
        }
        stage('QA with Checkstyle') {
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('Package with Maven') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Run Dockerfile') {
            steps {
                sh 'docker build -t myimg .'
            }
        }
        stage('Port Expose') {
            steps {
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }
    }
}
