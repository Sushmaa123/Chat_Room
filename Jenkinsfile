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
    post {
        always {
            emailtext(
                to: 'sushmaananda999@gmail.com',
                subject: 'Build ${BUILD_NUMBER} - ${BUILD_STATUS}',
                body: 'The build has completed with status: ${BUILD_STATUS}',
                attachLog: true
            )
        }
    }
}    
