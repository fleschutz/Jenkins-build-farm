pipeline {
    agent any  
    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/ninja-build/ninja', branch: 'master'
                script {
                    LATEST_TAG_COMMIT = sh ( script: 'git rev-list --tags --max-count=1', returnStdout: true ).trim()
                    LATEST_TAG_NAME = sh ( script: "git describe --tags ${LATEST_TAG_COMMIT}", returnStdout: true ).trim()
                    echo "Latest Git tag is: ${LATEST_TAG_NAME} (at commit hash ${LATEST_TAG_COMMIT})"
                }
                buildName "ninja ${LATEST_TAG_NAME}"
            }
        }
        stage ('Cleanup') {
            steps {
                sh 'git clean -xdf && git status'
	        }
	    }
        stage ('Build') {
            steps {
                sh 'cmake -Bbuild-cmake && cmake --build build-cmake'
            }
        }
        stage ('Unit Tests') {
            steps {
                sh './build-cmake/ninja_test'
            }
        }
    }
}