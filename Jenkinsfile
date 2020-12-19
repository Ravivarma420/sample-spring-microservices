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
 
}
    
}
