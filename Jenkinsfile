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
                sh 'pip install -r requirements.txt'
            }
        }
        stage("Tests"){
            steps{
                sh 'nose2'
            }
        }
        
    }
}