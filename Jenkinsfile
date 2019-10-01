pipeline {
    agent {
        kubernetes {
            defaultContainer 'jenkins-slave-java-maven'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}