pipeline {
  agent any 
    stages {
      stage ("Checkout") {
        steps {
          git url : "https://github.com/ankitamohanty1509/practicejenkins.git" , branch:"main"
        }
      }
    }
      stage("Installed") {
        script {
          sh "python3 -m venv venv"
    }
  }
  stage("status") {
    echo "successfull"
  }
}



       
