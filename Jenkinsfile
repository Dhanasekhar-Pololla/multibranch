pipeline{
    agent { label 'master'}
    stages {
  stage ('Build') {
    git url: 'https://github.com/Dhanasekhar-Pololla/multibranch/'
    withMaven {
      sh "mvn clean verify"
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
  }
}
}
