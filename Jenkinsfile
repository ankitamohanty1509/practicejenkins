pipeline {
  agent any 
    stages {
      stage ("Checkout") {
        steps {
          git url : "https://github.com/ankitamohanty1509/practicejenkins.git" , branch:"main"
        }
      }
       stage("Installed") {
        steps {
          sh """
          apt update 
          apt install -y python3.12-venv 
          apt install -y groovy 
          apt install -y openjdk-12-jdk maven
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



  
  



       
