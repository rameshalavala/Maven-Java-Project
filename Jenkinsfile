#!groovy

node {
        stage('Checkout'){

          checkout 'scm'
       }

       stage('Compiling'){

          sh 'mvn clean install'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    sh 'mvn sonar:sonar'
                }
	stage('artifact') {
                    //add stage sonar
                    archive 'target/*.war'
                }
    
	  /* stage('Deploy') {
                    
                    sh 'mvn sonar:sonar'
                }*/
}
