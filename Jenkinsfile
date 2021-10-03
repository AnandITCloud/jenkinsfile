
pipeline{
    agent any
    tools{
           maven 'mvn-3.8.2'
       }
    
    stages{
        stage('build'){
            steps{
                git 'https://github.com/wakaleo/game-of-life.git'
                sh 'mvn clean install'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat-server', path: '', url: 'http://13.235.94.92:8080')], contextPath: null, war: 'gameoflife-web/target/*.war'
            }
        }
        
    }
}