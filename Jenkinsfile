pipeline {
    environment{
            ENVIRONMENT_CREDENTIALS = credentials('docker')
    }
    agent{
        label 'Slave01'
    }

    stages {
        stage('git') {
            steps {
                git branch: 'main' , url: 'https://github.com/UmangKhandelwal23/PratisePRT2026'
            }
        }
        stage('docker') {
            steps {
                sh "sudo docker build -t umangkhandelwal/practiseprt:v1 ${WORKSPACE}"
                sh "sudo docker login -u ${ENVIRONMENT_CREDENTIALS_USR} -p ${ENVIRONMENT_CREDENTIALS_PSW}"
                sh 'sudo docker push umangkhandelwal/practiseprt:v1'
            }
        }
    }
}
