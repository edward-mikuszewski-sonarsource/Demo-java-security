pipeline {
    agent any
    tools {
      jdk 'JDK17'
      maven 'Default Maven'
      }
stages {
  stage('SCM') {
    steps {
        git url: 'https://github.com/edward-mikuszewski-sonarsource/Demo-java-security.git'
    }
  }
  stage('SonarQube Analysis') {
    steps {
    withSonarQubeEnv('EdSonar') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -DskipTests -Dsonar.projectKey=edward-mikuszewski-sonarsource_Demo-java-security_c5114eab-8eda-4f44-8ed3-c46921ec40c2 -Dsonar.projectName='Demo-java-security'"
    }
  }
}
}
}
