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
                // Клонируем строго твой репозиторий и твою ветку
                git branch: 'master', url: 'https://github.com/ROB-prog-cm/trainer-english.git'
            }
        }
		
        stage("Install Dependencies") {
            steps {
                // Ставим node_modules. Если используешь pnpm или yarn, замени на них
                sh "npm install"
            }
        }
		
        stage("Build Application") {
            steps {
                // Собираем статику (HTML/JS/CSS) в папку dist или build
                sh "npm run build"
            }
        }
    }
}
