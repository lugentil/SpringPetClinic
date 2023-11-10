pipeline{
    agent{label 'master'     
    }
    tools{maven 'M3'}
    stages{
        stage('CHECKOUT'){
            steps{
                git branch: 'main', url: 'https://github.com/lugentil/SpringPetClinic.git'
            }
        }
        stage('BUILD'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('TEST'){
            steps{
                sh 'mvn test'
            }
        }
        stage('PACKAGE'){
            steps{
                sh 'mvn package'
            }
        }
        stage('DEPLOY'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
