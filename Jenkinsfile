node{

    stage('SCM Checkout')
    {
       
        git 'https://github.com/VardhanNS/phpmysql-app'
    }
    
    stage('Run Docker Compose File')
    {
         
        sh 'docker build -t msuram/my-ecoomm:1.0 .'
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
