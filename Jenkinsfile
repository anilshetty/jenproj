pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                    sh 'python3 --version'
                    sh 'echo "Hello world! welcome to continous integration"'
                  }
                      }
        stage('deploy'){
            steps {
                retry(3){
                    sh 'echo "RETRYING"'
                }
                timeout(time: 2,unit: 'MINUTES'){
                    sh 'echo "DONE!"'
                }
            }
        }
         
    }
}
