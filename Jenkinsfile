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
          sh "python3 -m venv venv"
    }
  }
      stage("status") {
        steps {
          echo "successfull"
        }
      }
    }
}



  
  



       
