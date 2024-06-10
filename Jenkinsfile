node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=edward-mikuszewski-sonarsource_Demo-java-security_c5114eab-8eda-4f44-8ed3-c46921ec40c2 -Dsonar.projectName='Demo-java-security'"
    }
  }
}
