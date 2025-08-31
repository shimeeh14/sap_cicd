@Library('piper-lib-os') _

pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                script {
                    setupCommonPipelineEnvironment script: this
                }
            }
        }

        stage('CPI Deploy') {
            steps {
                script {
                    cpiUpload script: this
                }
            }
        }
    }
}
