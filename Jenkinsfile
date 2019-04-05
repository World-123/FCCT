pipeline {
  agent any
  stages {
    stage('code-pull') {
      steps {
        git(url: 'https://github.com/narendrasingamaneni91/FCCT.git', branch: 'Develop', credentialsId: 'narendrasingamaneni91')
      }
    }
    stage('build') {
      steps {
        bat '"C:\\\\Program Files\\\\7-Zip\\\\7z.exe" a -r test.zip -w . -mem=AES256'
      }
    }
    stage('git-tag') {
      steps {
        bat 'echo hello'
      }
    }
  }
}