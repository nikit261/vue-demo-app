pipeline {
    agent any
    stages{      
         stage('Install Dependencies') {
            steps {
                sh 'npm install'  
            }
        }    
        stage('Clean Build') {
            steps {
                    sh "echo Prod build for the app"
                    sh 'npm run build'
            }
        }
               
        stage('Deploying to Apache') {
            steps {
                    sh "cp -rf dist/* /var/www/html/VueProject/dist"
                    sh "sudo systemctl restart httpd"
            }
        }
    }
}
