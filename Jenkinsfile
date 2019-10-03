podTemplate(containers: [
        containerTemplate(name: 'java-maven'
        , image: 'bryceashey/jenkins-slave-java-maven'
        , ttyEnabled: true
        , envVars: [
            envVar( key: "JENKINS_SECRET", value: "0f82fc494e56f36adb8a3a06b37118edff7efa7bf208138916526a156fdd1b30")
            , envVar( key: "JENKINS_TUNNEL", value: "10.99.145.98:50000")
            , envVar( key: "JENKINS_AGENT_NAME", value: "${JENKINS_NAME}")
            , envVar( key: "JENKINS_NAME", value: "${JENKINS_NAME}")
            , envVar( key: "JENKINS_AGENT_WORKDIR", value: "/home/jenkins/agent")
            , envVar( key: "JENKINS_URL", value: "http://192.168.200.249:30735/")
        ])
    ]
    , podRetention: always()
  ) {

  node(POD_LABEL) {
    stage('Build a Maven project') {
      container('java-maven') {
          cat
      }
    }
  }
}