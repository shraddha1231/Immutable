pipeline{
	agent any
	tools{
	mvn 'MVN'
	}
	stages{
		stage('Checkout'){
			steps{
			git brach : 'master' , url: ""
			}
			}
		stage('Build'){
			steps{
			sh 'mvn clean install'
			}
			}
		stage('Test'){
			steps{
			sh 'mvn test'
			}
			}
		stage('Run Application'){
			steps{
			sh 'mvn exec:java -Dexec.mainClass="com.example.App"
			}
			}
	}
post{
sucess{
echo "build";
}
failure{
echo "fail";
}
}
}
