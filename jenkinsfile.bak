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
    stage('sonar scaning') {
	
	sh 'mvn sonar:sonar -Dsonar.host.url=http://3.110.27.218:9000 -Dsonar.login=cd8cc4cede48068dea8cf2f74cf9965d2d1439e0'
        
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