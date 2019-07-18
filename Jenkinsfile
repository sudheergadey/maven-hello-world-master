pipeline {
	agent any 
	stages{
		stage ('Compile stage'){
			steps {
			withMAven(maven : 'maven'){
	          sh 'mvn clean compile'
					}
	}
}
		stage ('testing stage') {
			steps {
			withMAven(maven : 'maven'){
	          sh 'mvn test'
					}
	      }
		}
		stage ('Deployment stage') {
			steps {
			withMAven(maven : 'maven'){
			  sh 'mvn deploy'
					}
		  }
		}
	}	
}
