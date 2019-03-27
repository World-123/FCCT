pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/narendrasingamaneni91/FCCT.git', branch: 'Develop', credentialsId: 'narendrasingamaneni91@gmail.com')
      }
    }
    stage('Zip') {
      steps {
        bat '"C:\\Program Files\\7-Zip\\7z.exe" a -r test.zip -w . -mem=AES256'
      }
    }
    stage('Deploy') {
      steps {
        sh '''curl -v -u admin:admin123 --upload-file test.zip http://localhost:8081/repository/suntrust/test.zip'''
      }
    }
  }
}
