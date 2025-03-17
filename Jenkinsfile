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
            bat 'mvn compile'
        }
      }
      stage('package') {
        steps {
            bat 'mvn package'
        }
      }
    }
}    