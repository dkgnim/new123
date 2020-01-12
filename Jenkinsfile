pipeline{
    agent {
        docker {image 'myimage'
        args '-u root --privileged -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages{
        stage ('Build') {
            steps {
                    git 'https://github.com/boxfuse/boxfuse-sample-java-war-hello.git'
                    sh 'mvn clean package'
                }
            }
            
        stage ('Build docker image') {
            steps {
                  
                sh 'cd /var/lib/jenkins/workspace/mvn/target/'
                
				git 'https://github.com/madgraycat/jenkins_ex.git' 
				sh 'sudo docker build -t myapp .'
            }
        }    
        }
    }
