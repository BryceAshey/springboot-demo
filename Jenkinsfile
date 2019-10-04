podTemplate(containers: [
        containerTemplate(name: 'jnlp'
        , image: 'bryceashey/jenkins-slave-java-maven'
        , ttyEnabled: true
        //, command: 'cat'
        )
    ]
    , podRetention: onFailure()
  ) {

  node(POD_LABEL) {
    stage('Build a Maven project') {
      container('jnlp') {        
        sh 'git clone https://github.com/BryceAshey/springboot-demo.git'
        sh 'cd springboot-demo'
        sh 'mvn -B clean package'
      }
    }
  }
}