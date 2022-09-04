pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  		    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '301215b5-9b0e-43aa-9ebf-69111a44e065', url: 'https://github.com/Ntizeah/https://github.com/Ntizeah/multibranch-demo.git']]])

  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
    	}
    }
  }
}
