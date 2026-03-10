pipeline {
    environment{
            ENIVRONMENT_CREDENTIALS = credentials('docker')
    }
    agent{
        label 'Slave01'
    }

    stages {
        stage('git') {
            steps {
                git branch: 'main' , url = 'https://github.com/UmangKhandelwal23/PratisePRT2026'
            }
        }
        stage('docker') {
            steps {
                sh 'sudo docker build -t umangkhandelwal/practiseprt:v1 /home/ubuntu/jenkins/workspace/FirstJob'
                sh 'sudo docker login -u ${ENIVRONMENT_CREDENTIALS_usr} -p ${ENIVRONMENT_CREDENTIALS_psw}'
                sh 'sudo docker push umangkhandelwal/practiseprt:v1'
            }
        }
    }
}
