pipeline {  
    agent any  
    stages {  
        stage ('Build') {  
            steps {  
                echo 'Running build phase...'
                
                echo 'Running build phase2222...'  
                sh '''
                pwd
                python3 manage.py runserver 0:5000 &
                '''
            }  
        }  
    }  
}  