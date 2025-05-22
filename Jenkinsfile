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
          sh "apt update && apt install -y python3.12-venv" 
          sh "apt install python3.12-venv"
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



  
  



       
