pipeline {  
    agent { label 'ubuntu_slave1' }  
    stages {  
        stage ('Build') {  
            steps {  
                echo 'Running build phase...'
                
                echo 'Running build phase2222...'  
                
                try{
                    sh '''
                pwd
                python3 manage.py runserver &
                
                ssh -t ubuntu@3.110.32.130 <<-EOF
                    if [ -d 'LoadStatic']
                    then
                        cd LoadStatic
                        git pull
                    else
                        git clone 'https://github.com/DharmikSA/LoadStatic.git'
                        cd LoadStatic
                    fi
                    pwd
                    nohup python3 manage.py runserver 0:8000 &   
EOF
                '''
                   mail bcc: '', body: 'Yes WOrk', cc: '', from: '', replyTo: '', subject: 'Manual Success', to: 'dharmiknakrani1690@gmail.com'

                }catch (Exception err) {
                   mail bcc: '', body: '$err', cc: '', from: '', replyTo: '', subject: 'Manual Success', to: 'dharmiknakrani1690@gmail.com'
                }
                
            }
        } 
      post 
    }  
}  
