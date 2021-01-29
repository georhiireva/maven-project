node{
    stage('Build') {
        bat 'mvn clean package'
        echo "Archiving"
        archiveArtifacts artifacts:'**/target/*.war'
    }
    stage('Deploy') {
        echo "Deploy step..."
    }
}
