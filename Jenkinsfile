pipeline {
    agent any

    tools {
        maven 'maven-3.8.6'
    }

    stage('git clone') {
	    steps {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/pav.git'
        
    }
	}
	stage('maven clean') {
	    stpes {         
	sh 'mvn clean'
    }    
    }
    
    stage('maven validate') {
	    stpes {
	sh 'mvn validate'
    }    
    }
    stage('maven compile') {
        stpes {
	sh 'mvn compile'  
    }
	}
	stage('maven test') {
        stpes {
	sh 'mvn test'  
    }
	}
	stage('maven package') {
        steps {
	sh 'mvn package'  
    }
	}
	stage('maven deployment') {
        stpes {
	sh 'mvn deploy'  
    }
	}
	
}