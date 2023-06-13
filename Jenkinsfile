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
                bat 'xcopy /Y /E /I C:\\Users\\Administrator\\.jenkins\\workspace\\angular-grade\\dist\\student-grade-tracker\\* C:\\var\\www\\html'
            }
        }

        stage('Docker Build') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'docker build -t sagarsaji/angular-gradee .'
            }
        }

         stage('Docker Run') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'docker run -d -it -p 80:80/tcp --name angular-gradee sagarsaji/angular-gradee:latest'
            }
        }
        
         stage('Docker Image') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'docker image ls'
            }
        }
        
        stage('Docker Push') {
            steps {
                git branch: 'main', credentialsId: 'ad63f2f4-0502-4bb9-bd0b-e2d047f54da8', url: 'https://github.com/sagarsaji/Grade_Calculator_Angular.git'
                bat 'docker push sagarsaji/angular-gradee:latest'
            }
        }
    }
}
