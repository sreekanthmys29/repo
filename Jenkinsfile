pipeline{

  agent{
    label devrelease
  }
  tools{
    maven 'maven3.9'

  }


  stages{
		stage('checkout'){
		
		steps{
		     git branch: 'testing', credentialsId: 'sreekanthmys29', url: 'https://github.com/sreekanthmys29/repo.git'
		
		}
		}
		stage('maven'){
		
		steps{
		     sh 'maven clean install'
		
		}
		}
		stage('Deploy'){
		
		steps{
		 deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://104.155.136.38:8085/')], contextPath: 'clientportal', war: 'clientportal.war'    
		
		}
		}


     }//stages

}//pipeline
