
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

        stage('Upload to CPI') {
            steps {
                script {
                    cpiUpload(
                        script: this,
                        host: 'https://dev-i77t4c8n.integrationsuite-trial.cfapps.us10-001.hana.ondemand.com',
                        credentialsId: 'prod-user',
                        integrationFlowId: 'demo_Iflow',
                        integrationFlowName: 'demo_Iflow',
                        packageId: 'DEMO_PACKAGE'
                    )
                }
            }
        }
    }
}
