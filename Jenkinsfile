pipeline {
    agent any

    stages {
        stage('test') {
            steps {

                echo 'Building anotherJob and getting the log'

                script {
                    echo "In the script"
                    def bRun = build 'anotherJob' 
                    echo 'last 100 lines of BuildB'
                    for(String line : bRun.getRawBuild().getLog(100)){
                        echo line
                    }
                }
            }
        }
    }
}
