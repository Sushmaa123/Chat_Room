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
