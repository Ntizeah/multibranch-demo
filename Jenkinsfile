pipeline{
  agent any
  stages{
  	stage('git-clone'){
  		steps{
  		    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '301215b5-9b0e-43aa-9ebf-69111a44e065', url: 'https://github.com/Ntizeah/https://github.com/Ntizeah/multibranch-demo.git']]])

  		}
  	}
    stage('parallel-level'){
      parallel{
        stage('sub-job1'){
          steps{
            echo "echo sub-job1 task"
            ech " testing second demo"
          }
        }
        stage('sub-job2'){
          steps{
            echo "sub-job2 task"
          }
        }
      }
    }
    stage('user-check'){
    	steps{
    		sh 'cat /etc/passwd |grep jenkins'
    	}
    }
  }
}
stage('version-check'){
  steps{
    echo "end of paralle job"
