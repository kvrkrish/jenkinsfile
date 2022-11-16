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
	stage('sonar scaning') {
        steps {
    sh 'mvn sonar:sonar -Dsonar.host.url=http://43.205.199.142:9000 -Dsonar.login=8fd313032d758940ee3890da37a5e5e3add9ef3c'
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