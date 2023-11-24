pipeline {
    agent any

    tools {
       maven 'Apache Maven 3.9.1'
    }

    stages {
        stage('git clone') {
            steps {
              git credentialsId: 'github', url: 'https://github.com/kartikeyapro/ks.git'
            }
        }
		stage('Maven Clean')
		{
		  steps {
		  sh 'mvn clean'
		  }
		}
		stage('Maven Test')
		{
		  steps {
		  sh 'mvn test'
		  }
		}
		stage('Maven compile')
		{
		  steps {
		  sh 'mvn compile'
		  }
		}
	    
        stage('Maven compile')
		{
		  steps {
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://3.85.227.113:9000 -Dsonar.login=9047b7a58b273a59b70799eabd48f0b23b9fc7dd'
		  }
		}		
				
		stage('Maven Package')
		{
		  steps {
		  sh 'mvn package'
		  }
		}
		stage('Maven Deploy')
		{
		  steps {
		  sh 'mvn deploy'
		  }
		}
	}
}
