pipeline{
    agent { label 'master'}
    tools {
        maven 'maven3'
    }
    stages{
        stage('Maven Build'){
            when {
                branch 'develop'
            }
            steps{
                sh "mvn clean package"
            }
        }
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                def pom = readMavenPom file: 'pom.xml'
                nexusArtifactUploader artifacts: [
                        [artifactId: 'multibranch', classifier: '', file: 'target/multibranch.war', type: 'war']
                    ], 
                    credentialsId: 'nexus3', 
                    groupId: pom.groupId, 
                    nexusUrl: '172.31.70.16:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'javahome-app', 
                    version: pom.version
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
