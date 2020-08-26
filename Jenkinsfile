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
        git branch: 'master',
    url: 'git@github.com:krarunraaj/Training.git'
        echo "KRAR"
      }
    }

  }
}
