node{
    stage('Build') {
        step
        sh 'mvn clean package'
        post {
            echo "Archiving"
            archiveArtifacts artifacts:'**/target/*.war'
        }
    }
    stage('Build') {
        sh 'mvn clean package'
    }
    stage('Deploy') {
        echo "Deploy step..."
    }
}