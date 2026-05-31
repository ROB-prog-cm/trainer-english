pipeline {
    agent { 
        label 'Jenkins-Agent' 
    }
	
    tools {
        jdk 'Java21'
        maven 'Maven3'
    }
    
    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
		
        stage("Checkout from SCM") {
            steps {
                // Адаптировали под твой репозиторий и твою ветку master
                git branch: 'master', credentialsId: 'github', url: 'https://github.com/ROB-prog-cm/trainer-english.git'
            }
        }
		
        stage("Build Application") {
            steps {
                sh "mvn clean package -DskipTests"
            }
        }
		
        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
