@Library("chaithulibs") _
pipeline{
    agent any
    stages{
       stage("Maven Build"){
            steps{
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage("Dev Tomcat Deploy"){
            steps{
                tomcatdeploy("172.31.0.198","ec2-user","tomcat-dev")
            }
        }
    }
}
