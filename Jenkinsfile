pipeline{
    agent any
    	environment {
		notifyEmail ="saroj.chandrabanshi@nagarro.com"
	}
    tools{
        maven 'Maven'
    }
    stages{
        stage("code checkout"){
            steps{
            bat "echo hello"
            }
        }   
        stage("code build"){
            steps{
            bat "mvn clean"
            }
        }
        stage("unit test"){
            steps{
            bat "mvn test"
            }
        }
        stage("Sonar Analysis"){
            steps{
            withSonarQubeEnv("testsonar")
                {
		    bat "echo Sonar Run half"
                        bat "mvn sonar:sonar"        
                }
            }
        }
        
    }
    post{
        success{
            bat "echo success"
            }
        }
}
