pipeline{
    agent {
        docker {image 'myimage'
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
                
                sh 'cd /var/lib/jenkins/workspace/mvn/target/ && docker build --tag=myapp' 
            }
        }    
        }
    }