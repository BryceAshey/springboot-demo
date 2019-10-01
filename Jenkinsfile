pipeline {
    agent {
        kubernetes {
            label 'jenkins-slave'
            defaultContainer 'jenkins-slave-java-maven'
            yaml """
  apiVersion: v1
  kind: Pod
  metadata:
   labels:
     name: jenkins-slave
   spec:
     containers:
     - name: jenkins-slave 
       image: bryceashey/jenkins-slave-java-maven
       workingDir: /home/jenkins
       command:
       - cat
         tty: true
"""
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