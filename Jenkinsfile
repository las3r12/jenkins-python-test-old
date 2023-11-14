pipeline {
    agent any
    stages {
        stage("Dependencies") {
            steps {
                python -m pip install -r requirments.txt
            }
        }
        stage("Tests"){
            steps{
                python test_main.py
            }
        }
        
    }
}