pipeline {
    agent{
        node{
            label 'Slave 1'
        }
    }

    stages {
        
        stage('Sonarqube-Scanning') {
            steps {
                script{
                    withSonarQubeEnv('Local_Sonarqube'){
                        def scannerHome = tool 'Sonarqube_Scanner'
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
       
    }
}
