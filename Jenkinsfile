pipeline {
    agent any
  //triggers {pollSCM('* * * * *')}
  stages {
    stage('Checkout') {
      steps {
        // Get some code from a GitHub repository
        git branch: "main", url: 'https://github.com/madhan-kumar-r/jenkins-docker-demo.git'
      }
    }
        stage('Build') {
      steps {
        //sh 'chmod a+x mvnw'
       // bat 'chmod a+x mvnw'
        bat './mvnw clean package -DskipTests=true'
      }

          post {
        always {
          archiveArtifacts 'target/*.jar'
        }
          }
        }
      /*  stage('DockerBuild') {
      steps {
        sh 'docker build -t jasdhir/emp-rest:latest .'
      }
        }*/

    

  }
}
