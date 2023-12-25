pipeline {
    agent any  // may run on any Jenkins node
    stages {
        stage ('Check') {
            steps {
                echo "Pulled from ${env.GIT_URL}, branch ${env.GIT_BRANCH}, commit {$env.GIT_COMMIT} ..."
                sh 'git fsck'
            }
        }
        stage ('Build') {
            steps {
		        echo "Starting build #${env.BUILD_NUMBER} on ${env.NODE_NAME} node ..."
                sh 'git clean -d --force'
                sh 'git status'
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
