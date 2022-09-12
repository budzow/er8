node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool '3.6.3';
    withSonarQubeEnv('SonarQube8') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=er8"
    }
  }
}
