pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    
    }
    stages {
        
        stage ('Built') {
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage ('Sonar Qube Analisys') {
            environment {
                scannerHome = tool 'vikrant-sonar-scan'
            }
            steps {
             
                withSonarQubeEnv('sonarqube-server') {
                   sh "${scannerHome}/bin/sonar-scanner"
            }
                
            }
        }
        
        
    }
}
