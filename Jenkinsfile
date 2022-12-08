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
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.85.212.120:8080')], contextPath: null, war: '**/*.war'
            }
        }
    }
}