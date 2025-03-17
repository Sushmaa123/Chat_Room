pipeline {
   agent any
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
      stage('build') {
        steps {
            bat 'mvn package'
        }
      }
    }
}    
