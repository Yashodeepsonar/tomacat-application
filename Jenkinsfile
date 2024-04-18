pipeline {
         agent any
	 tool{
maven'Maven 9.6'
	  }
         stages {
                 stage('Build') {
                 steps {
                     sh'mvn clean package'
                 }
			post{
success{
echo"Achiving the Artifacts"
achiveArtifacts artifacts: '**/*.war
                 }
}
}
                 stage('deploy to tomcat server') {
                 steps{
deploy adapters: [tomcat9(credentialsId: '8fcfe447-fbef-40e3-8166-b20bbfa233fa', path: '', url: 'http://localhost:3000/')], contextPath: null, war: '**/*war'
}
}
}
}
