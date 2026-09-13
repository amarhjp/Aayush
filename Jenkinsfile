pipeline {
    agent any 

    environment {
        // This is where Jenkins will copy your website on your local Linux machine
        DEPLOY_DIR = "/var/www/html/my-app"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building... Preparing HTML environment.'
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated validation checks...'
                // Run the script to check if index.html looks right
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying files to local directory..."
                // Create the web folder and copy index.html into it
                sh "mkdir -p ${DEPLOY_DIR}"
                sh "cp index.html ${DEPLOY_DIR}/"
                echo "Deployment finished successfully!"
            }
        }
    }
}

