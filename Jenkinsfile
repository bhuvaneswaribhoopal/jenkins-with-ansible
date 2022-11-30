pipeline{

agent{
label 'Ansiblenode'
}
environment{
AWSEC2_PRIVATEKEY=credentials('ec2-private-key')
}
stages{
stage('Checkoutcode'){
steps{
git credentialsId: 'e3037cf7-0062-4ca3-a5ad-398cf527cae8', url: 'https://github.com/bhuvaneswaribhoopal/jenkins-with-ansible.git'
}
}
stage ('RunAnsibleplaybook'){
steps{
sh "ansible-playbook -i inventory/walmart.hosts --private-key=$AWSEC2_PRIVATEKEY playbooks/installTomcat.yml
--ssh-common-args='-o StrictHostKeyChecking=no'"
}
}
}//stages closing
}//pipeline closing
