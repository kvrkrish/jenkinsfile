node {

    stage('git clone') {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/pav.git'
        
    }
	
    stage('clean') {
	
	bat 'mvn clean'
        
    }
    
    stage('validate') {
	
	bat 'mvn validate'
        
    }
    stage('compile') {
    bat 'mvn compile'  
    }
	stage('test') {
    bat 'mvn test'  
    }
	stage('package') {
    bat 'mvn package'  
    }
	stage('deploy') {
    bat 'mvn deploy'  
    }
	
}