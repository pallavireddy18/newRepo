pipeline{
	agent any
		stages{
			stage("compile stage")
			{
				steps
				withMaven(maven: 'maven 5.3'){
					sh 'mvn clean compile'
				}
			}
			stage("Testing stage")
			{
				steps
				withMaven(maven: 'maven 5.3'){
					sh 'sh mvn test'
				}
			}
			stage("Deployment stage")
			{
				steps
				withMaven(maven: 'maven 5.3'){
					sh 'sh mvn deploy'
				}
			}
		}
}