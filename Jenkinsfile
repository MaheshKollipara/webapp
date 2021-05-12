pipeline {
    agent any

     stages {
         stage("gitS"){
             steps{
                 git credentialsId: 'git_credentials', url: 'https://github.com/MaheshKollipara/webapp.git'
                  echo "THE MVN CLEANN BEGIN"
             }
         }
         stage ("buildS"){
             steps{
                 echo "THE MVN CLEANN BEGIN"
                bat 'mvn clean install'
                echo "THE MVN CLEANN END"
             }
         }
         stage ("deployS"){
             steps{
             deploy adapters: [tomcat9(credentialsId: '83b71ccb-436e-4412-9571-5c75aa43f440', path: '', url: 'http://localhost:9999')], contextPath: 'yourwebapp', war: '**/*.war'
            }
         }
}}