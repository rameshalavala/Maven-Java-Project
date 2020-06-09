#!groovy

node {
        stage('scm Checkout'){

          git 'https://github.com/rameshalavala/Maven-Java-Project'
       }

       stage('Compiling'){

	       sh "${mvnHome}/bin/mvn package"
       }
	   
      stage('Sonar') {
                    //add stage sonar
	      withSonarQubeEnv('sonarqube'){
		      sh "${mvnHome}/bin/mvn sonar:sonar"
                }
      }
	
}
