pipeline {
    agent any
    stages{
    stage("Git Checkout"){
         steps{
            git credentialsId: 'github', url:'https://github.com/dharanig746/cmrproject.git'
        }
        }
    stage("Maven build"){
        steps{
              sh "mvn clean install"
              }
             }
        stage('read pom')
     stage("Building image"){
         steps{
            sh "docker build -t cmrproject-repo/myapp:1.0 ."
            sh "docker run -dt cmrproject-repo/myapp:1.0 /bin/bash"
            sh "docker tag cmrproject-repo/myapp:1.0 monith/cmr-repo:1.0"
            sh "docker push monith/cmr-repo:1.0"
                    }
                  }
                 }
                }
