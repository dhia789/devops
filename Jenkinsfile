pipeline{
    agent{
        label "build-in"
    }

    environment {
        JAVA_HOME = '/var/lib/jenkins/tools/hudson.model.JDK/Java17'
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

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

        }

        stage("Test Application"){
            steps {
                sh "mvn test"
            }

        }
       
 
    }

}