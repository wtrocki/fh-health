node {
    // uncomment these 2 lines and edit the name 'node-4.4.5' according to what you choose in configuration
    def nodeHome = tool name: 'node-4.4.3', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"

    stage 'check environment'
    sh "node -v"
    sh "npm -v"
    //sh "grunt -v"

    stage 'checkout'
    checkout scm

    stage 'npm install'
    sh "npm install"

    stage 'frontend tests'
    sh "grunt fh:unit"

    stage 'packaging'
    sh "grunt fh:dist"
}
