podTemplate(containers: [
        containerTemplate(name: 'jnlp'
        , image: 'bryceashey/jenkins-slave-java-maven'
        , ttyEnabled: true
        //, command: 'cat'
        )
    ]
    , podRetention: always()
  ) {

  node(POD_LABEL) {
    stage('Build a Maven project') {
      container('jnlp') {        
        git clone 'https://github.com/BryceAshey/springboot-demo.git'
        cd springboot-demo
        sh 'mvn -B clean package'
      }
    }
  }
}