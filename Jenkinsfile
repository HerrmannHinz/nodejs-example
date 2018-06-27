/**
 * This pipeline will execute a nodejs build
 */

podTemplate(label: 'default', containers: [
  containerTemplate(name: 'node', image: 'node:9-stretch', ttyEnabled: true, command: 'cat')
  ]){
  node('default') {
    stage('Build a nodejs project') {
      git 'https://github.com/HerrmannHinz/nodejs-example.git'
      container('node') {
          sh 'ls -lha'
          sh 'apt-get update && apt-get install git python2.7'
          sh 'npm install'
      }
    }
  }
}
