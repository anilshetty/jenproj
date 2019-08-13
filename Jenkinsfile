pipeline {
    agent { docker { image 'python:2.7' } }
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
                    sh 'echo "DONE! wow"'
                }
            }
        }
         
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
