pipeline {
    agent any
    tools{
        maven "maven 3.9.9"
    }

    stages {
        stage('checkout') {
            steps {
                git "https://github.com/ScaleSec/vulnado"
            }
        }
        stage("Build"){
            steps{
                sh "mvn clean package"// compile et package le projet
            }
        }
        stage("Sonarqube Analysis"){
            steps{
                script{
                    def mvnHome= tool "maven 3.9.9"//utiliser le nom du tool maven configure dans jenskins
                    withSonarQubeEnv("SonarQ"){
                        sh "${mvnHome}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=Vulnado -Dsonar.projectName='Vulnado' "
                    }
                }
            }
        }
            
            
       
    }
}
