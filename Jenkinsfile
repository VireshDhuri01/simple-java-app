pipeline{
    tools{
        maven 'mvn'
    }
    agent any
    stages{
        stage('Basic'){
            steps{
                echo "This is the start of pipeline"
            }
        }
        stage('Git clone'){
            steps{
                git branch: 'main', url: 'https://github.com/VireshDhuri01/simple-java-app.git'
            }
        }
        stage('test the code'){
            steps{
                echo "testing the code  "
                sh 'mvn clean install'
            }
        }
        stage('archive jar') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }    
    }
}
