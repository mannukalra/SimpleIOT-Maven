node{
  stage ('cloning the repository'){
	git 'https://github.com/mannukalra/SimpleIOT-Maven.git'
  }
  stage ('Build') {
	withMaven(jdk: 'jdk8', maven: 'MVNLocal') {
      bat 'mvn clean install'
    } 
  }
  stage ("running appscan on cloud"){
      appscan application: '955fa556-8ef7-4279-8bdd-9114f5c58069', credentials: 'ASOC_Prod', name: 'SimpleIOTASOC_Test', scanner: static_analyzer('C:\\Users\\kalra_m\\eclipse-workspace\\SimpleIOT-Maven'), type: 'Static Analyzer'
  }
}
