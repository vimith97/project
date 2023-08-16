pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/mnt/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "sudo rm -rf /home/vimith/.m2/repository"
				
			}
		
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "sudo mvn clean install -DskipTests=true"
			
			}
			
		
		}
		
		stage ('deploy on docker container'){
		
				steps {
						
						sh "sudo docker-compose up"
						sh "sudo docker exec 
					
						}
				
				}
	
	
	
	}
		
}
