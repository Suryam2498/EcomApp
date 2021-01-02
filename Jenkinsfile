node{

    stage('SCM Checkout')
    {
       
        git 'https://github.com/VardhanNS/phpmysql-app'
    }
    
    stage('Run Docker Compose File')
    {
         git 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
       
        withCredentials([string(credentialsId: 'docker-pwd', variable: 'DockerHubPwd')]) 
        {
            sh "docker login -u msuryam -p ${DockerHubPwd}"
        }
        sh 'docker push msuryam/sur_ecomm'
    }
}
