@Library('piper-lib-os') _

piperPipeline {
    stages = [
        Init: [
            script: {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/shimeeh14/sap_cicd.git',
                        credentialsId: 'github'
                    ]]
                ])
            }
        ],

        DeployDev: [
            script: {
                integrationSuiteDeploy(
                    host: "https://dev-i77t4c8n.integrationsuite-trial.cfapps.us10-001.hana.ondemand.com",
                    username: ${{ secrets.CPI_USER }},
                    password: ${{ secrets.CPI_PASS }},
                    artifactId: "demo_Iflow",
                    packageId: "DEMO_PACKAGE",
                    filePath: "demo_Iflow.zip"
                )
            }
        ],
    ]
}
