pipeline {
  agent any
  tools {
    maven 'maven'
    }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
        }
      }

    stage ("Clone repo"){
      steps {
        sh "git clone https://github.com/Sawssen19/TP-Sonarqube.git"
        }
      }


    stage ("Build"){
      steps {
        dir("TP-Sonarqube"){
          sh "mvn clean install"
          }
        }
      }

    stage ("SonarQube Analysis"){
      steps {
        withSonarQubeEnv("sonar-server")          
          dir("TP-Sonarqube"){
            sh "mvn sonar:sonar"
            }
          }
        }
      }
  }
