pipeline {
    agent any 
    tools {
        // same as global tool configuration
        maven 'apache-maven-3.0.1'
    }
    stages {
        stage('version verify') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('build') {
            steps {
                echo 'Compiling App'
                dir('worker') {
                    sh 'mvn compile'
                }
            }
        }
        stage('test') {
            steps {
                echo 'Running tests against defined rules'
            }
        }
    }
    post {
        always {
            echo 'Job finished'
        }
        sucess {
            echo 'All steps succeeded'
        }
        failure {
            echo 'Unsuccessful Run'
        }
    }
}