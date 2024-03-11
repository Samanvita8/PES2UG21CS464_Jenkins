pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Compile the .cpp file using shell script
                sh 'g++ -o output hello.cpp'
            }
        }
        stage('Test') {
            steps {
                // Print output of .cpp file using shell script
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                // Your deployment steps here
            }
        }
    }
    
    post {
        // Execute this block after every stage
        always {
            // Display 'pipeline failed' in case of any errors
            catchError {
                echo 'Pipeline succeeded'
            }
            catchError {
                echo 'Pipeline failed'
            }
        }
    }
}
