pipeline {
agent {
label 'build server'
}

stages {

stage ('Checkout') 
{
steps
    {
    
        checkout scm
        
    }
    
}
stage ('Build1') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/newp/account-service ; mvn clean install " 
    }
}
    stage ('dockerbuild') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/newp/account-service ; sudo docker build -t account-service . " 
    }
}
  stage ('dockerimagepush') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/newp/account-service ; sudo docker login -usuramdev -pRavidocker123 " 
        sh "cd /home/ubuntu/workspace/newp/account-service ; sudo docker tag account-service suramdev/account-service "
        sh "cd /home/ubuntu/workspace/newp/account-service ; sudo docker push suramdev/account-service "
    }
}
    stage ('k8deployment')
      {
          steps {
              node ('ansible') {
                 sh " cd /root : sudo ansible-playbook kubernetes.yml"
              }
          }
      }          
}
    
}
