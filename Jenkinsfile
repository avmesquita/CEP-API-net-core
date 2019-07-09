pipeline {
  agent any
   
  environment {
	dotnet = 'path\to\dotnet.exe'
  } 
  stages {	  
    stage('Cloning Git') {
      steps {
        git 'https://github.com/avmesquita/CEP-API-net-core'
      }
    }        
    stage('Restore Packages') {
      steps {
        bat 'dotnet restore'	    
      }
    }     
    stage('Clean') {
      steps {
        bat 'dotnet clean'	    
      }
    }     
    stage('Build Release') {
      steps {
         bat 'dotnet build --configuration Release'
      }
    }   	  	  	
    stage('Publish') {
      steps {
         bat 'dotnet publish -c Release -o out'
      }
    }   	  	  
  }
}
