pipeline {
agent any
stages {

stage('checkout'){
steps {
git 'https://github.com/LovesCloud/java-tomcat-maven-example'

}
}
stage ('compile stage'){
steps {
	//get maven home path
def mvnHome = tool name: 'maven 3.6.3', type: 'maven'
	sh "${mvnHome}/bin/mvn package"
}
}
stage ('testing stage'){
steps {
def mvnHome = tool name: 'maven 3.6.3', type: 'maven'
	sh "${mvnHome}/bin/mvn test"
}
}
stage ('Deployment stage'){
steps {
def mvnHome = tool name: 'maven 3.6.3', type: 'maven'
	sh "${mvnHome}/bin/mvn deploy"

}
}
}
}
