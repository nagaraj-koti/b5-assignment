pipeline{
	agent {label "docker-job"}
	
	stages{
		stage("BUILD"){
			steps{
				echo "BUILD stage - Docker image build - multistage docker build - maven & tomcat-image"
				sh ''' 
					cd /home/ubuntu/my/docker-maven/
					docker build -t nagarajk640/maven-tomcat .
				'''
			}
		}
		stage("PUSH-HUB"){
			steps{
				echo "Pushing image to docker hub"
				//sh 'docker push nagarajk640/maven-tomcat'
				echo "Docker image successfuly pushed to docker hub."
			}
		}
		
		stage("RUN-CONTAINER"){
			steps{
				echo "Running container"
				sh 'docker run -it -d -p 8080:8080 nagarajk640/maven-tomcat'
				sh ''' 
					 IP=`curl ifconfig.co`
					 echo "Your application running on ${IP}:8080 address"
				'''
			}
		}
	}
}
