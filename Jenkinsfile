pipeline {
     agent any
     
     tools {nodejs "nodejs"}
     
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                
            }
        }
        stage("Deploy") {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
