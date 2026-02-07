pipeline {
    agent any // This is the mandatory definition at the top
    
    stages {
        stage('Run Node Test') {
            steps {
                // Now you run your specific node version inside a container via shell
                sh 'docker run --rm node:24.13.0-alpine3.23 node --eval "console.log(process.platform,process.env.CI)"'
            }
        }
    }
}
