node{

    stage('SCM Checkout')
    {
       
        git 'https://github.com/Suryam2498/EcomApp.git'
    }
    
   stage('Run Docker Compose File')
    {
        sh 'sudo docker rm -f php_app mysqli'
       sh  'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
   
    }
    
     stage('PUSH image to Docker Hub')
    {
       
      // withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerhubPwd')]) {
      //      sh " sudo docker login -u msuryam -p ${dockerhubPwd}"
     //  }
    
     sh 'sudo docker login -u msuryam -p suryam123'
      sh "sudo docker tag ecommapp_web msuryam/sur_ecomm:${BUILD_NUMBER}"
        sh "sudo docker push msuryam/sur_ecomm:${BUILD_NUMBER}"
    }
    
    
}
