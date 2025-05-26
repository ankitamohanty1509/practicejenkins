pipeline {
  agent any {
    environment {
      Image_Name = "ankitamohanty1509/simpleapp"
      Docker-Credentials = credentials("docker-credentials")
    }
    stages {
      stage ("checkout") {
        steps {
          git url: "https://github.com/ankitamohanty1509/practicejenkins.git" , branch: "main"
      }
      stage ("Install tools") {
        steps {
          sh ''' 
          apt-get update 
          apt install -y maven 
          apt install -y python3 python3-venv
          apt install -y openjdk-17-jdk
          java --version
          python3 --version
          mvn --version
          '''
        }
      }
      stage ("Docker Build") { 
        steps {
          sh "docker build -t $Image_Name:latest ."
        }
       }
      stage ("Docker Push") {
        steps {
          sh '''
          echo "$Docker-Credentials-PWD | docker login -u $Docker-Credentials-USR --password-stdin"
          docker push $Image_name:latest
          '''
        }
      }
      stage ("Docker run")
        steps {
          sh "docker run -d --name $Image_name -p 8080:80 $Iamge-name:latest"
        }
      }
    }
      post {
        success {
          echo "successfull"
        }
        failed {
          echo "failed"
        }
      }
    }
  }
      
            
        
      

  
  



       
