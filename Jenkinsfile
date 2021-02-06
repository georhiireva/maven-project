node{
    stage('Build') {
        bat 'mvn clean package'
        echo "Archiving"
        archiveArtifacts artifacts:'**/target/*.war'
    }
    stage('Deploy to staging') {
        build job: 'deploy_to_staging'
    }
    stage('Deploy to prod') {
        timeout(time:5, unit:'DAYS') {
            input mesage:'Approve prod deployment?'
        }    
        build job:'deploy_to_prod'
    }
}
