pipeline{
	agent any
	stages{
		stage('scm checkout')
		{
				steps
				{
					git branch: 'master', url: 'https://github.com/Manisha-jharbade/maven-project'
				}
		}
		stage('validate code')
		{
			steps{
				withMaven(jdk: 'localJDK-1.8', maven: 'localmaven') {
				sh 'mvn validate'
				}
			}
		}
		stage('compile code')
		{
			steps
			{
				withMaven(jdk: 'localJDK-1.8', maven: 'localmaven') 
				{
					sh 'mvn compile'
				}
			}
		}
			
	}
}
