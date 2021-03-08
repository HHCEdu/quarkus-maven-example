pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        withMaven(jdk: 'JavaSDK_8u221', maven: 'Maven_3_5_3')
        sh 'mvn clean install'
      }
    }

  }
}