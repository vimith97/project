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
						sh "sudo docker exec -itd mysql_container create database test;"
						sh "sudo docker exec -itd mysql_container use database test;"
						sh "sudo docker exec -itd mysql_container CREATE TABLE `USER` (
  `id` int(10) unsigned NOT NULL auto_increment,
  `first_name` varchar(45) NOT NULL,
  `last_name` varchar(45) NOT NULL,
  `email` varchar(45) NOT NULL,
  `username` varchar(45) NOT NULL,
  `password` varchar(45) NOT NULL,
  `regdate` date NOT NULL,
  PRIMARY KEY  (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;"
						sh "sudo docker exec -itd mysql_container select * from USER;"
					
					
						}
				
				}
	
	
	
	}
		
}
