pipeline {
    agent any

    tools {
        maven 'maven-3.8.6'
    }
    stages {
    stage('git clone') {
	    steps {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/pav.git'
        
    }
	}
	stage('maven clean') {
	    steps {         
	sh 'mvn clean'
    }    
    }
    
    stage('maven validate') {
	    steps  {
	sh 'mvn validate'
    }    
    }
    stage('maven compile') {
        steps  {
	sh 'mvn compile'  
    }
	}
	stage('maven test') {
        steps  {
	sh 'mvn test'  
    }
	}
	stage('maven package') {
        steps {
	sh 'mvn package'  
    }
	}
	stage('maven deployment') {
        steps  {
	sh 'mvn deploy'  
    }
	}
}	
}