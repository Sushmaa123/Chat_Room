pipeline {
   agent any
   tools {
    maven 'maven3'
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
      stage('build') {
        steps {
            sh 'mvn package'
        }
      }
    }
}    
