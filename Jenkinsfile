pipeline {
    agent {
        kubernetes {
            defaultContainer 'jenkins-slave-java-maven'
        }
    }
    stages {
        stage('Build') { 
            steps {
                container('jenkins-slave-java-maven') {
                    sh 'mvn -B -DskipTests clean package' 
                }
            }
        }
    }
}