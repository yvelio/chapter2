
   
pipeline {
  agent any
    tools {
      			maven 'maven3'
            jdk 'JDK11'
    }
    stages {   
      stage('Build maven ') {
            steps { 
                    sh 'pwd'      
                    sh 'mvn  clean install -DskipTests'
            }
        }
           
        stage('Build image ') {
            steps { 
                    sh 'pwd'      
                    sh 'mvn  clean package -Dquarkus.container-image.push -Dquarkus.container-image.build=true  -Dquarkus.kubernetes.deploy=true'
            }
        }
    }
}