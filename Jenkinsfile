pipeline {
     agent any

     stages {
         
         stage("test") {
             steps {
                 echo "Testing the aplication..."
             }
         }

        stage("build") {
            steps {
                 echo "Building the application..."
            }
        }

        stage("deploy") {
             steps {
                 echo "Deploying the application..."
             }
        }

     }

     post {
    success {
      slackSend  message: "✅ Build was good: ${env.JOB_NAME} #${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
    failure {
      slackSend  message: "❌ FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
    unstable {
      slackSend  message: "⚠️ UNSTABLE: ${env.JOB_NAME} #${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
    aborted {
      slackSend  message: "🛑 ABORTED: ${env.JOB_NAME} #${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
  }
}