//SCRIPTED 
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
		agent any
		stages {
			stage('build') {
				steps {
					echo "Build"
				}
			}
			stage('Test') {
				steps {
					echo "Test"
				}
			}
			stage('Integration Test') {
				steps {
					echo "Integration Test"	
				}
			}
		}		
	}