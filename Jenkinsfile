pipeline {
    agent any
    stages {
        stage("Dependencies") {
            steps {
                sh 'python3 -m pip install -r requirments.txt'
            }
        }
        stage("Tests"){
            steps{
                sh 'python test_main.py'
            }
        }
        
    }
}