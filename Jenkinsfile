pipeline{
    agent any
    stages{
        stage('github validation'){
          steps{
                 git url: 'https://github.com/akshu20791/addressbook-cicd-project'
          }
        }
        stage('compiling the code'){
          steps{
                 sh 'mvn compile'
          }
        }
        stage('testing the code'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa of the code'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage("deploy the project on tomcat"){
            steps{
                sh "sudo cp /opt/venu/workspace/pipeline/target/addressbook.war /home/ubuntu/apache-tomcat-9.0.100/webapps/"
            }
        }
    }
}
