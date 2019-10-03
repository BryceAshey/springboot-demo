podTemplate(containers: [
        containerTemplate(name: 'jnlp'
        , image: 'bryceashey/jenkins-slave-java-maven'
        , ttyEnabled: true
        , command: 'cat'
        )
    ]
    , podRetention: always()
  ) {

  node(POD_LABEL) {
    stage('Build a Maven project') {
      git 'https://github.com/BryceAshey/springboot-demo.git'
      container('jnlp') {
          sh 'mvn -B clean package'
      }
    }
  }
}