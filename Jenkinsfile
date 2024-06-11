pipeline {
    agent any
    tools {
      jdk 'JDK17'
      }
stages {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv('EdSonar') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -DskipTests -Dsonar.projectKey=edward-mikuszewski-sonarsource_Demo-java-security_c5114eab-8eda-4f44-8ed3-c46921ec40c2 -Dsonar.projectName='Demo-java-security'"
    }
  }
}
}
