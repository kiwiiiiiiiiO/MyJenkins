pipeline {
    agent{
        node{
            label 'slave1'
        }
    }

    stages {
        
//         stage('Sonarqube-Scanning') {
//             steps {
//                 script{
//                     withSonarQubeEnv('sonarqube-container'){
//                         def scannerHome = tool 'LocalSonarQubeScanner'
//                         sh "${scannerHome}/bin/sonar-scanner -X"
//                     }
//                 }
//             }
//         }
        stage('SonarQube analysis') {
//             tools {
//                 jdk "jdk11" // the name you have given the JDK installation in Global Tool Configuration
//             }
            environment {
                scannerHome = tool 'LocalSonarQubeScanner' // the name you have given the Sonar Scanner (in Global Tool Configuration)
            }
            steps {
                withSonarQubeEnv(installationName: 'sonarqube-container') {
                    sh "${scannerHome}/bin/sonar-scanner -X"
                }
            }
        }
       
    }
}


