properties([
  parameters([
    string(name: 'DEPLOY_ENV', defaultValue: 'TESTING', description: 'The target environment', )
   ])
])





pipeline {
  agent any
  
  stages {
    stage('Import TT Data') {
      steps {
        deleteDir()
        git branch: 'master', credentialsId: '06:61:54:53:2c:28:fc:66:45:b9:0b:db:78:bf:38:d1' ,
    url: 'ssh://git@github.com:krarunraaj/ThreeGuys.git'
        echo "KRAR"
      }
    }

  }
}
