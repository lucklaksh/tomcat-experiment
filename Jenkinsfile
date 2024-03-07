pipeline{
    agent any
    tools{
        maven 'local_maven'
    }

    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'

            }

        }
        stage('Deploy to Tomcat Server'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat -server-password', path: '', url: 'http://54.147.204.111:8000')], contextPath: null, war: '**/*.war'

            }

        }
    }
}
