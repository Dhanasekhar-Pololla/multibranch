pipeline{
    agent { label 'master'}
    stages {
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                script {
                    def pom=readMavenPom file: 'pom.xml'
                    nexusArtifactUploader artifacts: [
                        [artifactId: 'multibranch', classifier: '', file: 'target/*.war', type: 'war']
                    ], 
                        credentialsId: 'nexus3', 
                        groupId: pom.groupId, 
                        nexusUrl: '172.31.30.108:8081',
                        nexusVersion: 'nexus3',
                        protocol: 'http', 
                        repository: 'Dhana-app', 
                        version: pom.version
                }
            }
        }

        stage('Deploy to Dev'){
            when {
                branch 'develop'
            }
            steps{
                echo "coming soon.."
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
                echo "coming soon.."
            }
        }

    }
}
