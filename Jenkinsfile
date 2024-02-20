pipeline {
    agent any

    tools {
       maven 'maven-3.9.6'
    }

    stages {
        stage('git clone') {
            steps {
              git credentialsId: 'github', url: 'https://github.com/vkp1133/ks.git'
            }
        }
		stage('Maven version')
		{
		  steps {
		  sh 'mvn --version'
		  }
		}
		stage('Maven Clean')
		{
		  steps {
		  sh 'mvn clean'
		  }
		}
		stage('Maven validate')
		{
		  steps {
		  sh 'mvn validate'
		  }
		}
		stage('sonar scan')
		{
		  steps {
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://16.170.141.195:9000 -Dsonar.login=2b3d40882ef4eb5adba65dbdc83ad126aa001e0d'
		  }
		}
		
		stage('Maven compile')
		{
		  steps {
		  sh 'mvn compile'
		  }
		}
		stage('Maven Test')
		{
		  steps {
		  sh 'mvn test'
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




