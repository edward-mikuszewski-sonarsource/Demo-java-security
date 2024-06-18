node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv('EdSonar') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=edward-mikuszewski-sonarsource_Demo-java-security_571e050e-3d84-45fd-ac15-14c230d8c53b -Dsonar.projectName='Demo-java-security'"
    }
  }
}
