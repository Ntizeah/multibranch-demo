pipeline {
    agent any
    stages {
    	stage('clone'){
           steps{
              checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '301215b5-9b0e-43aa-9ebf-69111a44e065', url: 'https://github.com/Ntizeah/multibranch-demo.git']]])


           }
    	}
        stage('Main Branch Deploy Code') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo "Building Artifact from Main branch"'
 
                sh 'echo "Deploying Code from Main branch"'
            }
        }
        stage('Develop Branch Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                sh 'echo "Building Artifact from Develop branch"'
                sh 'echo "Deploying Code from Develop branch"'
           }
        }
    }
}
