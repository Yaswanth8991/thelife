pipeline {
    agent any
    tools {
        maven 'maven'
    }

    stages {
        
        stage ('build') {
            steps {
                sh 'mvn clean package'
            }
            
        }
        stage('deploy') {
            steps {
                sshagent(['tomcatcred']) {
    sh 'scp -o StrictHostKeyChecking=no target/petclinic.war ubuntu@35.90.139.3:/opt/apache-tomcat-8.5.81/webapps'
}
                
            }
        }
    }
}
