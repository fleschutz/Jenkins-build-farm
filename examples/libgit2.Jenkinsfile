pipeline {
    agent any  
    stages {
        stage ('Checkout') {
            steps {
               git url: 'https://github.com/libgit2/libgit2', branch: 'main'
               script {
                    LATEST_TAG_COMMIT = sh ( script: 'git rev-list --tags --max-count=1', returnStdout: true ).trim()
                    LATEST_TAG_NAME = sh ( script: "git describe --tags ${LATEST_TAG_COMMIT}", returnStdout: true ).trim()
                    echo "Latest Git tag is: ${LATEST_TAG_NAME} (at commit hash ${LATEST_TAG_COMMIT})"
                }
                buildName "libgit2 ${LATEST_TAG_NAME}"
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
                sh 'cmake . && make'
            }
        }
        stage ('Test') {
            steps {
                sh 'ctest -V'
            }
        }
    }
}