pipeline {
    agent any

    tools {
        maven 'maven-3.8.6'
    }

    stage('git clone') {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/pav.git'
        
    }
	stage('maven clean') {
	
	sh 'mvn clean'
        
    }
    
    stage('maven validate') {
	
	sh 'mvn validate'
        
    }
    stage('maven compile') {
    
	sh 'mvn compile'  
    }
	stage('maven test') {
    
	sh 'mvn test'  
    }
	stage('maven package') {
    
	sh 'mvn package'  
    }
	stage('maven deployment') {
    
	sh 'mvn deploy'  
    }
	
}