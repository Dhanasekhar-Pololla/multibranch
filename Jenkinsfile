pipeline{
    agent { label 'master'}
    stages{
        stage("build & SonarQube analysis") {
            steps {
              withSonarQubeEnv('sonar7') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                nexusArtifactUploader artifacts: [
                        [artifactId: 'multibranch', classifier: '', file: 'target/*.war', type: 'war']
                    ], 
                    credentialsId: 'nexus3', 
                    groupId: 'in.javahome', 
                    nexusUrl: '172.31.70.16:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'http://3.209.82.68:8081/repository/javahome-app/', 
                    version: '1.0'
            }
        }
        stage

        stage('Deploy to Dev'){
            when {
                branch 'develop'
            }
            steps{
                echo "coming soon.. "
            }
        }

        stage('Deploy to QA'){
            when {
                branch 'release'
            }
            steps{
                echo "coming soon.."
            }
        }

        stage('Deploy to Prod'){
            when {
                branch 'master'
            }
            steps{
                echo "coming soon. ."
            }
        }
    }
}
