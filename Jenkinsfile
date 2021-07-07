pipeline {
    agent { label "master" }

    stages {
        stage('Hello') {
            steps {
                git branch: 'Dev', changelog: false, credentialsId: 'Agent_007_1.9', poll: false, url: 'https://github.com/vivek4545/Addsudousers.git'
            }
        }
        stage ('Execute ansible plybook') {
        steps {
            withCredentials([usernamePassword(credentialsId: 'Agent_007_1.9', passwordVariable: 'Ansible_pass', usernameVariable: 'Ansible_user')]) 
            {
          sh "ansible-playbook -i inventory/invent.txt sudorights.yml -e 'ansible_user=$Ansible_user' -e 'ansible_pass=$Ansible_pass'"
}
        }
            
        }
    }
}
