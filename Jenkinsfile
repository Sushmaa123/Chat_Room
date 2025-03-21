pipeline {
   agent any
   tools {
    maven 'maven'
   }
   stages {
      stage('git checkout') {
        steps {
            git credentialsId: 'git-ssh', 
                url: 'git@github.com:Sushmaa123/Chat_Room.git'
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
