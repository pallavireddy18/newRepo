pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            when { tag "release-*" }
            steps {
                echo 'Deploying only because this commit is tagged...'
                bat 'mvn deploy'
            }
        }
        stage('emailNotification'){
		    steps{
			    emailext ( 
		       subject: "Job Build", 
		       body: "Job Build Success.${env.JOB_NAME} [${env.BUILD_NUMBER}]",
		       to: "badal.singh2432@gmail.com,pallavireddy.s18995@gmail.com"
		     )
		    }
	    }
    }
}
