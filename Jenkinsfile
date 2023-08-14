pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/data/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "rm -rf /home/vimith/.m2/repository"
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "sudo mvn clean install -DskipTests=true"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh "sudo cp -r target/LoginWebApp.war /mnt/apache-tomcat-9.0.78/webapps/"

						}
				
				}
	
	
	
	}
		
}
