pipeline{
    agent any
    stages{
        stage('Build') {
            steps{
                withEnv(['PATH+EXTRA=/usr/sbin:/usr/bin://sbin:/bin'])
                sh ''' mvn clean package '''
            }
            post {
                success {
                    echo "Now Archiving..."
                    archiveArtifacts artifacts: "**/target/* .war"
                }
            }
        }
    }
}