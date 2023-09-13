pipeline {
    agent any
    stages {
        stage (git) {
            steps {
                git 'https://github.com/vamsibyramala/dicet_tv.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://52.66.201.42:8081/')], contextPath: 'vamsi', war: '**/*.war'
            }
        }
    }
    
}
