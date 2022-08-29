@Library("chaithulibs") _
pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            steps{
                git credentialsId: 'github-creds', url: 'https://github.com/chaithugagan/Myapp-2022'
            }
        }
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
