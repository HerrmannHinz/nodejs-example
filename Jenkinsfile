/**
 * This pipeline will execute a nodejs build
 * + output the version of the java installation (to give you the idea) 
 */

podTemplate(label: 'frontend', containers: [
  containerTemplate(name: 'myAwesomeNodeContainer', image: 'node:10-stretch', ttyEnabled: true, command: 'cat'),
  containerTemplate(name: 'myAwesomeJavaContainer', image: 'java:alpine', ttyEnabled: true, command: 'cat')
  ]){
  node('frontend') {
    stage('Build a nodejs project') {
      git 'https://github.com/HerrmannHinz/nodejs-example.git'
      container('myAwesomeNodeContainer') {
          sh 'npm install'
      }
    }
    stage('some java test') {
      container('myAwesomeJavaContainer') {
          sh 'java -version'
      }
    }
  }
}
