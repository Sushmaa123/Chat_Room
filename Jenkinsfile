pipeline {
   agent any
   tools {
    maven 'maven'
   }
   stages {
      stage('git checkout') {
        steps {
            git 'https://github.com/Sushmaa123/Chat_Room.git'
        }
      }
      stage('compile') {
        steps {
            sh 'mvn compile'
        }
      }
      stage('package') {
        steps {
            sh 'mvn package'
        }
      }
    }
}    
