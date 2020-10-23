pipeline{
    agent { label 'master'}
    stages {
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                script {
                    def repository = pom.version.endsWith('SNAPSHOT') ? 'javahome-app-snapshot' : 'javahome-app'
                    nexusArtifactUploader artifacts: [
                        [artifactId: 'multibranch', classifier: '', file: 'target/multibranch.war', type: 'war']
                    ], 
                        credentialsId: 'nexus3', 
                        groupId: 'in.javahome', 
                        nexusUrl: '172.31.30.108:8081',
                        nexusVersion: 'nexus3',
                        protocol: 'http', 
                        repository: 'http://3.23.20.245:8081/repository/Dhana-app/', 
                        version: '2.0-SNAPSHOT'
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
