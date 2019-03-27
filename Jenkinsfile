pipeline {
  agent any
  stages {
    stage('codepull') {
      steps {
        git(url: 'https://github.com/narendrasingamaneni91/FCCT.git', branch: 'Develop', credentialsId: 'narendrasingamaneni91@gmail.com')
      }
    }
    stage('build-zip') {
      steps {
        bat '"C:\\\\Program Files\\\\7-Zip\\\\7z.exe" a -r test.zip -w . -mem=AES256'
      }
    }
    stage('deploy') {
      steps {
        bat 'nexus.bat'
      }
    }
  }
}
