node{
    stage('Build') {
        bat 'mvn clean package'
        echo "Archiving"
        archiveArtifacts artifacts:'**/target/*.war'
    }
    stage('Deploy to staging') {
        build job: 'deploy_to_staging'
    }
}
