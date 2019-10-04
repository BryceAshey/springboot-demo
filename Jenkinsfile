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
    checkout scm
    stage('Pull Source') {
      container('jnlp') {        
        sh 'git clone https://github.com/BryceAshey/springboot-demo.git'
      }
    }
    stage('Build') {
      container('jnlp') {
        sh 'mvn -B clean package'
      }
    }
  }
}