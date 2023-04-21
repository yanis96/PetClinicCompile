pipeline{
    agent any
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/yanis96/PetClinicCompile.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
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
                ls
                pwd
                sh 'java -jar /var/jenkins_home/workspace/PetClinicDeclarative/target/*.jar'
            }
        }
    }
}
