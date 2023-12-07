pipeline {
    agent any
    
        stages {
        
        
stage("Package") {
    steps {
        sh "./gradlew build"
        
    }
}
stage("Docker build") {
    steps {
        sh "docker build -t localhost:5000/calculator ."
        
    }
}
stage("Docker push") {
    steps {
sh "docker push localhost:5000/calculator"
    }
 }
    stage("Déploiement sur staging") {
    steps {
        sh "docker run -d --rm -p 8765:8080 --name calculator localhost:5000/calculator"
    }
}     
    }
   
   
  }  

