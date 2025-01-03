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
       
    }
}
