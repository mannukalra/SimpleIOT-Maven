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
      appscan application: '18f3c3ca-a689-e811-ad5d-00259057d989', credentials: 'ASOC_Prod', name: 'ASOC_Prod', scanner:static_analyzer('C:\Users\kalra_m\eclipse-workspace\SimpleIOT-Maven'), type: 'Static Analyzer'
  }
}
