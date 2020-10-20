pipeline{
    agent { label 'master'}
    stages{
        stage('Maven Build'){
           
            steps{
                sh "mvn clean package"
            }
        }
    }
}
