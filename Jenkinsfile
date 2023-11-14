pipeline {
    agent any
    stages {
        stage("Dependencies") {
            steps {
                "python -m pip install -r requirments.txt"
            }
        },
        stage("Tests"){
            "python test_main.py"
        }
        
    }
}