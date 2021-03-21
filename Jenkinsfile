pipeline {
    agent any
    parameters{
        string(name: "ENVIRONMENT", description: 'dev,prod', defaultValue: '')
    }
    stages {
        stage('Test Jenkins call Ansible'){
            steps {
                sh'''
                    sudo ansible-playbook -i /home/ec2-user/win-lab/Ansible/inventory/hosts -e "env=${ENVIRONMENT}"  /home/ec2-user/win-lab/Ansible/installnginx.yml
                '''
            }
        }
    }
}    
