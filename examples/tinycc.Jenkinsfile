// Pipeline script for tinycc
pipeline {
    agent any  
    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/TinyCC/tinycc', branch: 'mob'
                script {
                    LATEST_TAG_COMMIT = sh ( script: 'git rev-list --tags --max-count=1', returnStdout: true ).trim()
                    LATEST_TAG_NAME = sh ( script: "git describe --tags ${LATEST_TAG_COMMIT}", returnStdout: true ).trim()
                    echo "Latest Git tag is: ${LATEST_TAG_NAME} (at commit hash ${LATEST_TAG_COMMIT})"
                }
                buildName "tinycc ${LATEST_TAG_NAME}"
            }
        }
        stage ('Cleanup') {
            steps {
                sh 'git clean -xdf && git status'
	        }
	    }
        stage ('Build') {
            steps {
                sh './configure && make'
            }
        }
        stage ('Tests') {
            steps {
                sh 'make test'
            }
        }
    }
}