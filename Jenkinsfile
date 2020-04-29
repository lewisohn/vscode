pipeline {
	agent {
    kubernetes {
      label 'vscode'
      yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: yarn-build
    image: node:lts-buster
    command:
    - cat
    tty: true
"""
    }
  }
  stages {
    stage('Build') {
      steps {
        container('yarn-build') {
					sh '''
					yarn
					yarn compile
					'''
        }
      }
    }
  }
}
