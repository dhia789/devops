pipeline{
    agent{
        label "build-in"
    }

     
    tools {
        jdk 'Java17'
        maven 'Maven3'
        
    }
 

    stages{
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }

        }
   
        stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/dhia789/devops'
            }

        }

        
       
 
    }

}