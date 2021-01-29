node{
    stage('Build') {
        bat 'mvn clean package'
        post {
            echo "Archiving"
            archiveArtifacts artifacts:'**/target/*.war'
        }
    }
    stage('Deploy') {
        echo "Deploy step..."
    }
}
