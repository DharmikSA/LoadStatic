pipeline {  
    agent any  
    stages {  
        stage ('Build') {  
            steps {  
                echo 'Running build phase...'
                
                // echo 'Running build phase2222...'  
                sh '''
                pwd
                python3 manage.py runserver &
                '''

                sh '''
                ssh -t ubuntu@3.110.32.130 <<-EOF
                   apt install python3-django
                   if [ -d 'LoadStatic']
                   then
                     cd LoadStatic
                     git pull
                   else
                     git clone 'https://github.com/DharmikSA/LoadStatic.git'
                     cd LoadStatic
                   fi
                   nohup python3 manage.py runserver 0:8000 &
                   EOF

                '''
            }  
        }  
    }  
}  