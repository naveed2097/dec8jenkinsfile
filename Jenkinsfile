pipeline {
	agent any
	
	stages{
		stage('Git'){
			steps{
				echo "clone repo"
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git_cred', url: 'https://github.com/naveed2097/dec8jenkinsfile']]])
			}
		}
		stage('Compile'){
			steps{
				echo "compiling the script"
				bat 'mvn compile'
			}
		}
		stage('Package'){
			steps{
				echo "compiling the project"
				bat 'mvn package'
			}
		}
		stage('Dependency'){
			steps{
				echo "installing project dependency"
				bat 'mvn install'
			}
		}
		stage('Test'){
			steps{
				echo "testing the project"
				bat 'mvn test'
			}
		}
	}
}