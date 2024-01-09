pipeline {
    agent {
        label "build-in"
    }

    environment {
        def javaHome = tool name: 'Java17', type: 'jdk'
        PATH = "${javaHome}/bin:${env.PATH}"
        JAVA_HOME = "${javaHome}"
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