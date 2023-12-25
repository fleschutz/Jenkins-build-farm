pipeline {
    agent any  // may run on any Jenkins node
    stages {
        stage ('Build') {
            steps {
                echo "Pulled from ${env.GIT_URL}, branch ${env.GIT_BRANCH}, commit {$env.GIT_COMMIT} ..."
                echo "Starting build number ${env.BUILD_NUMBER} ..."
            }
        }
        stage ('Test') {
            steps {
                echo "Our build needs to be tested..."
            }
        }
        stage ('Zip') {
            steps {
                sh 'zip -r sample-build.zip .'
            }
        }
        stage ('Archive') {
            steps {
                archiveArtifacts artifacts: 'sample-build.zip', fingerprint: true, onlyIfSuccessful: true
            }
        }
    }
}
