pipeline {
    agent { 
        label 'Jenkins-Agent' 
    }
    
    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
		
        stage("Checkout from SCM") {
            steps {
                git branch: 'master', url: 'https://github.com/ROB-prog-cm/trainer-english.git'
            }
        }
		
        stage("Install Dependencies") {
            steps {
                sh "yarn install"
            }
        }
		
        stage("Build Application") {
            steps {
                sh "yarn run build"
            }
        }
    }
}
