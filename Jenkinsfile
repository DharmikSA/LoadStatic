pipeline {  
    agent any  
    stages {  
        stage ('Build') {  
            steps {  
                echo 'Running build phase...'
                
                echo 'Running build phase2222...'  

                sh '''
                pkill -f runserver
                pwd
                nohup python3 manage.py runserver 0:8000 &
                '''
            }  
        }  
    }  
}  