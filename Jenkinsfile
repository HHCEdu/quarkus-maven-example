node('docker') {
  stage('Poll') {
    checkout scm
  }
  stage('Build & Unit test'){
    sh 'mvn clean verify -DskipITs=true';
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }
  stage('Static Code Analysis'){
    sh 'mvn clean verify sonar:sonar -Dsonar.projectName=quarkus-maven-example -Dsonar.host.url=http://129.213.112.244:9000 -Dsonar.projectKey=quarkus-maven-example -Dsonar.projectVersion=$BUILD_NUMBER';
  }
}
