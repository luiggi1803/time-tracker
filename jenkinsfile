pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: '0b804251-347e-4cfe-94d7-f393e99457eb', path: '', url: 'http://ec2-3-16-164-253.us-east-2.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/time-tracker-web-0.5.0-SNAPSHOT.war'
            }
        }        
    }
}
