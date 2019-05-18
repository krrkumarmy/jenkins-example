pipeline {
		agent any 
			stages 	{
					stage ('SCM checkout') {
					git ('https://github.com/krrkumarmy/jenkins-example.git') }
				
				stage ('sonar') {
				 steps {
					 withSonarQubeEnv('sonar') {
					 withMaven (maven:'localMaven')
					 {
					  sh 'clean install sonar:sonar'
					  }
					  }
					  }
				}
				
				stage ('build and sonarqube analysis') {
					steps  {
						withSonarQubeEnv('sonar') {
					 withMaven('maven :localMaven') {
					 sh 'mvn clean package sonar:sonar'
					 }
					 }
					 }
				}
					 }
					 }
