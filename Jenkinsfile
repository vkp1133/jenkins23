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
