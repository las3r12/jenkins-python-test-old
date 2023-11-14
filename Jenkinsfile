pipeline {
    agent {
        docker {
            image 'python:latest'
            args '-u root'
        }
    }
    stages {
        stage("Dependencies") {
            steps {
                sh 'pip install -r requirments.txt'
            }
        }
        stage("Tests"){
            steps{
                sh 'python test_main.py'
            }
        }
        
    }
}