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
        bat '\'"C:\\Program Files\\7-Zip\\7z.exe" a -r test.zip -w . -mem=AES256\''
      }
    }
    stage('git-tag') {
      steps {
        sh '''#!/bin/bash
sh("git config user.email narendrasingamaneni91@gmail.com")
sh("git config user.name narendrasingamaneni91")

sh "git remote set-url origin https://github.com/narendrasingamaneni91/FCCT.git"

sh "git tag -a narendra -m \\"passed CI\\""
// deletes tag on remote in order not to fail pushing the new one
sh "git push origin :refs/tags/narendra"
// pushes the tags
sh "git push --tags"'''
      }
    }
  }
}