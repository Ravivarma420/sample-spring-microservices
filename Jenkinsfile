pipeline {
agent {
label 'latestnode'
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
       sh "cd /home/ubuntu/workspace/project1/account-service ; mvn clean install " 
    }
}
 
}
    
}
