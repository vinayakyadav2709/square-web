pipeline {
    agent {
        // This tells Jenkins to run the whole pipeline inside a Docker container
        docker { 
            image 'node:20-alpine' 
            args '-u root' // Ensures permission to write to the workspace
        }
    }

    stages {
        stage('Install') {
            steps {
                echo 'Installing dependencies inside container...'
                sh 'npm ci' 
            }
        }

        stage('Build') {
            steps {
                echo 'Running Next.js build...'
                // Next.js build output will be saved to the .next folder in your workspace
                sh 'npm run build'
            }
        }
    }

    post {
        success {
            echo 'Build complete! Your .next folder is ready.'
        }
    }
}
