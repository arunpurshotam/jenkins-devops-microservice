//SCRIPTED 
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
		agent any
		//agent {docker {image 'node:13.8'}}
		environment{
			dockerHome = tool 'MyDocker'
			mavenHome = tool 'MyMaven'

			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}

		stages {
			stage('checkout') {
				steps {
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD_NUMBER - $env.BUILD_NUMBER"
					echo "BUILD_ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"
				}
			}

			stage('compile') {
				steps {
					sh "mvn clean compile"
				}
			}

			stage('test') {
				steps {
					sh "mvn test"
				}
			}

			stage('integration Test') {
				steps {
					sh "mvn failsafe:integration-test failsafe:vefiry"
				}
			}
		} 
		post {
			always{
				echo 'I am awesome, I run always'
			}
			success{
				echo 'I run when you are successful'
			}	
			failure{
				echo 'I run when it fails'
			}
			//changed {}
			//unstable {}
		}		
	}