pipeline {
    agent any

    stages {

        stage('Install Node Modules') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'npm install'
            }
        }
        
         stage('Build') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'ng build --configuration=production'
            }
        }

        stage('Copy') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'xcopy C:\\Users\\Administrator\\.jenkins\\workspace\\angular-grade\\dist\\student-grade-tracker\\* C:\\var\\www\\html /E /H'
            }
        }
    }
}
