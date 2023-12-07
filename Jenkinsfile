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
        
    }
    post {
always {
mail to: 'majidlearning7@gmail.com',
subject: "Cher lion Votre compilation est terminée: ${currentBuild.fullDisplayName}",
body: " Votre build est accompli, Veuilez vérifier: ${env.BUILD_URL}"
}
}
   
  }  

