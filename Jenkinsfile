pipeline{
    agent any
    environment
    {
        PATH = "$PATH:/usr/share/apache-maven-3.6.3/"
    }
    stages
    {
       stage('GetCode')
       {
            steps
            {
                git 'https://github.com/durgavinaym/maven1.git'
            }
         }  
          stage('SonarQube Analysis')
          {
            withSonarQubeEnv(Sonarqube-9.4)
           {
            sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=java"
           }
        }
    }
}      
