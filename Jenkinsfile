/**
 * This pipeline will execute a nodejs build
 */

podTemplate(label: 'frontend', containers: [
  containerTemplate(name: 'node10', image: 'node:10-stretch', ttyEnabled: true, command: 'cat'),
  containerTemplate(name: 'javasomething', image: 'java:openjdk-8-jre-alpine', ttyEnabled: true, command: 'cat')
  ]){
  node('frontend') {
    stage('Build a nodejs project') {
      git 'https://github.com/HerrmannHinz/nodejs-example.git'
      container('node10') {
          sh 'npm install'
      }
    }
    stage('some java test') {
      container('javasomething') {
          sh 'java --version'
      }
    }
  }
}
