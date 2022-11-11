node {

    stage('git clone') {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/pav.git'
        
    }
	
    stage('clean') {
	
	sh 'mvn clean'
        
    }
    
    stage('validate') {
	
	sh 'mvn validate'
        
    }
    stage('compile') {
    
	sh 'mvn compile'  
    }
	stage('test') {
    
	sh 'mvn test'  
    }
	stage('package') {
    
	sh 'mvn package'  
    }
	stage('deployment') {
    
	sh 'mvn deploy'  
    }
	
}