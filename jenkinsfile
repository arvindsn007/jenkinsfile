pipeline {
   agent {label 'slave-1'}

    stages {
        stage('GIT-CHECKOUT') {
            steps {
                echo 'This is Git Checkout Stage'
                git 'https://github.com/arvindsn007/java_repo1.git'
            }
        }
        stage('BUILD') {
            steps {
                echo 'This is build Stage'
                sh ' mvn clean install'
            }
        }
        stage('TOMCAT-START') {
            steps {
                echo 'This is TOMCAT START CODE'
                sh ' sudo /home/ubuntu/./tomcatstart'
            }
        }
        stage('DEPLOY') {
            steps {
                echo 'This is deploy Stage'
                sh 'sudo cp target/*.war /home/ubuntu/tomcat/webapps'
            }
        }
    }
}
