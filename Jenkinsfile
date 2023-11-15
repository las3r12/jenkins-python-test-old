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
                sh 'python -m nose2'
                sh 'python -m coverage run main.py'
                sh 'python -m coverage html'
                sh 'python -m coverage xml'
                sh 'python -m coverage report'
                sh 'pycobertura show --format html --output coverage.html coverage.xml'
            }
        }
    }
    post{
        always {
            archiveArtifacts artifacts: 'coverage.html', onlyIfSuccessful: true
        }
    }
}