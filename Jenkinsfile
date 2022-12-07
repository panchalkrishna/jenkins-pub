pipeline{
    agent any 
                
    tools{
        maven 'maven-3.8.6'
    }
    stages{
        stage ('Build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to tomcat server') {
            steps{

                echo "Deployment"
            }
        }
    }
}