pipeline {
  agent any
  
  stages {
    stage('Build') {
      steps {
        // Use a build automation tool like Maven to compile and package the code
        // Example:
        sh 'mvn clean install'
      }
      post {
        success {
          emailext body: "The stage 'Build' was successful",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
        failure {
          emailext body: "The stage 'Build' failed",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
      }
    }
    
    stage('Unit and Integration Tests') {
      steps {
        // Use test automation tools like JUnit or TestNG for unit and integration tests
        // Example:
        sh 'mvn test'
      }
      post {
        success {
          emailext body: "The stage 'Unit and Integration Tests' was successful",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
        failure {
          emailext body: "The stage 'Unit and Integration Tests' failed",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
      }
    }
    
    // Add post blocks with email notification configuration for other stages as well
    
    stage('Code Analysis') {
      steps {
        // Use a code analysis tool like SonarQube or Checkstyle
        // Example:
        sh 'mvn sonar:sonar'
      }
      post {
        success {
          emailext body: "The stage 'Code Analysis' was successful",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
        failure {
          emailext body: "The stage 'Code Analysis' failed",
                   subject: "[Pipeline] ${currentBuild.result}: Job '${env.JOB_NAME}'",
                   to: 'dskaveesh@gmail.com',
                   attachLog: true
        }
      }
    }
    
    // Add post blocks with email notification configuration for other stages as well
    
  }
}
