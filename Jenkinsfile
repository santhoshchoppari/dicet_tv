pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  

stages {
      stage("GET the code from git")
	{
        	  steps
		{
            		git branch: 'master', url: 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
          
          	}
      }
      stage("build the code")
	{
          	steps
		{
              		sh "mvn clean package"
          	}
      }
      stage("deploy THE CODE")
	{
        	 steps
		{
             		deploy adapters: [tomcat9(credentialsId: 'tommmm', path: '', url: 'http://3.110.163.89:8080/')], contextPath: 'TEST', war: '**/*.war'
          	}
      	}
  }
}
