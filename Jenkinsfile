pipeline {
    agent{
        node{
            label 'slave1'
        }
    }

    stages {
        
        stage('Sonarqube-Scanning') {
            steps {
                script{
                    withSonarQubeEnv('sonarqube-container'){
                        def scannerHome = tool 'Local_SonarQubeScanner'
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
       
    }
}
