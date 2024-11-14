pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages {
        stage('chekout'){
            steps{
                git branch : 'main' , url : 'https://github.com/rayann007/SpringPetClinic.git'
            }
        }
    
        stage ('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage ('test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
            
        }
        stage('Deploy'){
            steps{
                sh 'java-jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/.jar'
            }
    
        }    
    }
    
}
