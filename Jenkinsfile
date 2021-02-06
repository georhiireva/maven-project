node{
    pipelineTriggers {
        pollSCM('*/5 * * * *')
    }
    stage('Build') {
        bat 'mvn clean package'
        echo "Archiving"
        archiveArtifacts artifacts:'**/target/*.war'
    }
    stage('Test') {
        bat 'chcp'
        bat 'chcp 1251'
        bat 'chcp'
    }
    stage('Deployments') {
        parallel staging: {bat 'copy **/target/*.war C:/Apache/apache-tomcat-9.0.41/webapps'},
                    prod: {bat 'copy **/target/*.war C:/Apache/apache-tomcat-9.0.41_prod/webapps'}
    }  
}
