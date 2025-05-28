pipeline{
	agent any
	tools{
		gradle 'Gradle'
		jdk 'JDK'
	}
	
	stages{
		stage('Checkout'){
			steps {
				git branch : 'main' , url : 'https://github.com/ayushRajar/GradleApp.git'
			}
		}
		
		stage('Build'){
			steps {
				sh 'gradle build'
			}
		}
		
		stage('Test'){
			steps{
				sh 'gradle test'
			}
		}
		
		stage('Run Application'){
			steps {
				sh 'gradle run'
			}
		}
	}
	post {
		success {
			echo 'Successfully build the project'
		}
		
		failure {
			echo 'Build and Deployment Failed'
		}
	}
}
