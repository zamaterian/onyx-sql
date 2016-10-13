try {

    node {
        stage "Setup"
            checkout scm

        stage "Dependencies"
            lein "-U deps"

        stage "Deploy"
            lein "with-profiles deployer deploy"
            }

} catch(e) {
    currentBuild.result = "FAILURE"
    notifyFailed(e.message)
    throw e
}
