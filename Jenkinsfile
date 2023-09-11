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
		}		
	}