// Jenkinsfile for GitHub project 'jhead'
// --------------------------------------
// Description: Nightly builds of jhead (master branch) from https://github.com/Matthias-Wandel/jhead.
// Log Rotation: 10 builds maximum recommended
// GitHub project: https://github.com/Matthias-Wandel/jhead/
// Timeplan: @midnight
// Pipeline script:
pipeline {
    agent any // may run on any Jenkins node
    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/Matthias-Wandel/jhead', branch: 'master'
                script {
                    LATEST_TAG_COMMIT = sh ( script: 'git rev-list --tags --max-count=1', returnStdout: true ).trim()
                    LATEST_TAG_NAME = sh ( script: "git describe --tags ${LATEST_TAG_COMMIT}", returnStdout: true ).trim()
                    echo "Latest Git tag is: ${LATEST_TAG_NAME} (at commit hash ${LATEST_TAG_COMMIT})"
                }
                buildName "jhead ${LATEST_TAG_NAME}"
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
                sh 'make'
            }
        }
        stage ('Test') {
            steps {
                sh './jhead -h || true'
            }
        }
        stage ('Archive') {
            steps {
                archiveArtifacts artifacts: 'jhead', fingerprint: true, onlyIfSuccessful: true
            }
        }
    }
}
