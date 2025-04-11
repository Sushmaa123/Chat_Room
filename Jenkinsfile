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
            sh 'mvn install'
        }
      }
    }
   post {
        always {
            emailext(
                to: 'sushmaananda999@gmail.com',
                subject: 'Build ${BUILD_NUMBER} - ${BUILD_STATUS}',
                body: 'The build has completed with status: ${BUILD_STATUS}',
                attachLog: true
            )
        }
    }
}    
