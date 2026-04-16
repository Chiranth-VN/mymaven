pipeline{
	agent any
	tools{
	maven 'Maven'
	jdk 'JDK11'
	}
	
	stages
	{
		stage('checkout')
		{
		steps{
			git branch : 'master' , url:'https://github.com/Chiranth-VN/mymaven.git'
		}
		}
		
		stage('Build')
		{
		steps{
		sh 'mvn clean package'
		}
		}
		
		stage('Test')
		{
		steps{
		sh 'mvn test'
		}
		}
		
		stage('Run-Application')
		{
		steps{
		sh 'java -jar target/MyMavenApp01-1.0-SNAPSHOT.jar'
		}
		}
	}
	
	post
	{
	success
	{
	echo 'build success'
	}
	failure{
	echo 'build failure'
	}
	}
}
