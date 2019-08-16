pipeline {
	agent any

	tools {
	   maven 'Maven 3.5.4'
	}

	stages {
	   stage('Build') {
	      steps {
	         echo 'Building...'
	         sh 'mvn clean compile'
	      }
	   }

	   stage('Package') {
	      steps {
	         echo 'Deploying...'
	         sh 'mvn -DskipTests package'
	         archiveArtifacts artifacts: '**/target/*.jar', fingerprint :true
	         }
	      }
	   }
	}
