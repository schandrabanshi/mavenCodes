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
            withSonarQubeEnv("Test_SonarQube")
                {
		    bat "echo Sonar Run half"
                        bat "mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.1.2184:sonar"        
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
