pipeline{
	agent any
	stages{
		stage('1-clone'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '6a94cd96-5180-492d-b3ff-1f7d6d9a98f9', url: 'https://github.com/etech-team5group2/Team5-App.git']])
			}

		}
		stage('2-systemscheck'){
			steps{
				sh'sudo systemctl status jenkins'
			}
		}
		stage('3-diskcheck'){
			steps{
				sh'df -h'
			}
		}
		stage('4-blockcheck'){
			steps{
				sh'lsblk'
			}
		}
        stage('5-ops-check'){
            steps{
                sh'cat /etc/os-release'
            }
        }
	    stage('6-script-control'){
             steps{
            sh 'bash -x /var/lib/jenkins/workspace/Team5App/script.sh'
            }  
        }

    }
}

