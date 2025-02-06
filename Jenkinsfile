pipeline {
    agent any
    stages {      
        stage("Copy file to Docker server"){
            steps {
				
                sh "scp -r /var/lib/jenkins/workspace/66026213-html/* root@43.208.253.87:~/66026213-html"
            }
        }
        
        stage("Build Docker Image") {
            steps {
                //path yaml files
				ansiblePlaybook playbook: '/var/lib/jenkins/workspace/66026213-html/playbooks/build.yaml'
            }    
        } 
        
        stage("Create Docker Container") {
            steps {
                //path yaml files
				ansiblePlaybook playbook: '/var/lib/jenkins/workspace/66026213-html/playbooks/deploy.yaml'
            }    
        } 
    }
}
