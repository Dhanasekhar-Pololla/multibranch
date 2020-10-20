pipeline{
    agent { label 'master'}
        stage('Upload to Nexus'){
            when {
                branch 'develop'
            }
            steps{
                echo "coming soon.."
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
