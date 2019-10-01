podTemplate(containers: [
        containerTemplate(name: 'java-maven', image: 'bryceashey/jenkins-slave-java-maven', ttyEnabled: true, command: 'cat', podRetention: 'onFailure')
  ]) {

  node(POD_LABEL) {
    stage('Build a Maven project') {
      container('maven') {
          cat
      }
    }
  }
}