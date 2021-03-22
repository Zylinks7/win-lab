pipeline {
	agent any
		parameters{
			string(name: "ENVIRONMENT", description: 'dev,prod', defaultValue: '')
		}
	options {
		timestamps()
		ansiColor('xterm')
	}
		
	stages {
		stage('Test Jenkins call Ansible'){
			steps {
				script {
					if(param.ENVIRONMENT == "dev") {
						sh'''
							echo "ENVIRONMENT: ${ENVIRONMENT}"
							sudo ansible-playbook -i /home/ec2-user/win-lab/Ansible/inventory/hosts -e "env=${ENVIRONMENT}"  /home/ec2-user/win-lab/Ansible/installnginx.yml
							'''
					}
					elas if (parma.ENVIRONMENT == "prod") {
						sh'''
							echo "ENVIRONMENT: ${ENVIRONMENT}"
							sudo ansible-playbook -i /home/ec2-user/win-lab/Ansible/inventory/hosts -e "env=${ENVIRONMENT}"  /home/ec2-user/win-lab/Ansible/installnginx.yml
							'''	
					}
					elas {
						sh 'echo "Environment not found. Please try agin."'
					}
				}
			}
		}
		stage('Clean WS') {
			steps {
				cleanWs()
			}
		}

	}
}    
