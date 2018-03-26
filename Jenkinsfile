pipeline {
    agent any

    stages {
        stage('test') {
            steps {

                echo 'Building anotherJob and getting the log'

                script {
                    def bRun = build 'anotherJob' 
                    echo 'last 100 lines of BuildB'
                    for(String line : bRun.getRawBuild().getLog(100)){
                        echo line
                    }
                }
            }
        }
        stage('Build') {
            docker.image('python:3.5.1').inside {
                sh 'python --version'
            }
        }
    }
}
