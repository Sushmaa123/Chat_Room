def COLOR_MAP = [
    'SUCCESS': 'good',
    'FAILURE': 'danger'
    ]
pipeline {
   agent any
    environment {
     SCANNER_HOME = tool 'sonar-scanner'
    }
   stages {
      stage('git checkout') {
        steps {
            git 'https://github.com/Sushmaa123/Chat_Room.git'  
        }
      }
      stage('code analysis') {
        steps {
            withSonarQubeEnv('sonar-server') {
                sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Chat_Room \
               -Dsonar.java.binaries=. \
               -Dsonar.projectKey=Chat_Room'''
               }
        }
      }
      stage('docker build') {
        steps {
            script {
              sh 'docker build -t chat-room .' 
            }
      }
    }
   stage('docker container') {
         steps {
            script {
               sh 'docker run -itd --name chat-room -p 8082:8080 chat-room'
              }
          }
    }    
 } 
   post {
        always {
            echo 'slack Notification.'
            slackSend channel: '#jenkins-docker-m9',
            color: COLOR_MAP [currentBuild.currentResult],
            message: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URl}"
            
        }
    }

}    
