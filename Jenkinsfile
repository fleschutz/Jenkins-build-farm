pipeline {
    agent any
    stages {
        stage ('Hi') {
            steps {
                echo "Hello World!"
            }
        }
        stage ('Build') {
            steps {
                sh 'echo "Hello World!" > generatedFile.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'generatedFile.txt', onlyIfSuccessful: true
        }
    }
}
