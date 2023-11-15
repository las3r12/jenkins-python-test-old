pipeline {
    agent {
        docker {
            image 'python:latest'
            args '-u root'
        }
    }
    stages {
        stage("dependencies") {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage("tests"){
            steps{
                sh 'python -m coverage run -m nose2'
                
            }
        }

        stage("report"){
                sh 'python -m coverage xml'
                sh 'python -m coverage html'
                sh 'python -m coverage report'
        }
    }
    post{
        always {
            archiveArtifacts 'htmlcov/*'
            cobertura coberturaReportFile : 'coverage.xml'
        }
    }
}