pipeline {
 agent any
 
 tools {
 // here you need to install Maven Tool in Jenkins and declare here
 maven 'my-maven'
 }
 stages {
 stage('GitCheckout') {
 steps {
 echo 'Git Cloning and Checkout Started...'
 git 'https://github.com/JonSnow10-1/DevOpsAddressBook.git'
 //git branch: 'main', credentialsId: 'git', url: 'https://github.com/JonSnow10-
 //DevOpsAddressBook-Private.git'
 // git credentialsId: 'git', url: 'https://github.com/JonSnow10-1/DevOpsAddressBook￾Private.git'
 echo 'Git Cloning and Checkout Successful...'
 }
 }
 stage('Compile & Build') {
 steps {
 echo 'Compile and Build Started...'
 sh 'mvn clean compile'
 echo 'Compile and Build Successful...'
 }
 } 
 stage('Test') {
 steps {
 echo 'Testing Started...'
 sh 'mvn test'
 echo 'Testing Successfull...'
 }
 }
 stage('Package') {
 steps {
 echo 'Packaging Started...'
 sh 'mvn clean package'
 echo 'Packaging Successful...'
 }
 } 
 stage('Archive Artifacts') {
 steps {
 echo 'Archiving the Artifacts Started...'
 archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
 echo 'Archiving the Artifacts Completed...'
 }
 }
 stage('Webhook Trigger') {
 steps {
 echo 'Build triggered automatically using webhook...'
 }
 }
 }
}
