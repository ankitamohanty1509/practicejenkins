pipeline {
  agent any 
    stages {
      stage ("Checkout") {
        steps {
          git url : "https://github.com/ankitamohanty1509/practicejenkins.git" , branch:"main"
        }
      }
       environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
       stage("Installed") {
        steps {
          sh """
          apt update 
          apt install -y python3.12-venv 
          apt install -y groovy 
          apt install -y openjdk-17-jdk maven
          """
    }
  }
      stage("Docker build") {
        steps {
          sh "docker build -t hello-world ."
        }
      }
      stage("run container") {
        steps {
          sh "docker run hello-world"
        }
      }
      stage("status") {
        steps {
          echo "successfull"
        }
      }
    }
}



  
  



       
