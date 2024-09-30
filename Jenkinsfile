// Jenkins Pipeline sample script to build and test something 
pipeline {
    agent any 
    stages {
	stage ('Build Name') {
            steps {
                script {
                    LATEST_TAG_COMMIT = sh ( script: 'git rev-list --tags --max-count=1', returnStdout: true ).trim()
                    LATEST_TAG_NAME = sh ( script: "git describe --tags ${LATEST_TAG_COMMIT}", returnStdout: true ).trim()
                    echo "Latest Git tag is ${LATEST_TAG_NAME} at commit hash ${LATEST_TAG_COMMIT}."
                }
                buildName "${LATEST_TAG_NAME}"
            }
        }
        stage ('Cleanup') {
            steps {
                sh 'git clean -xdf && git status'
            }
        }
        stage ('Build') {
            steps {
		echo "Starting build #${env.BUILD_NUMBER} on ${env.NODE_NAME} node ..."
		// e.g. ./configure && make
            }
        }
        stage ('Tests') {
            steps {
                echo "Starting tests..."
		// e.g. make tests
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
