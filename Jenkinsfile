pipeline {
  agent {
    kubernetes {
      defaultContainer "yarn-build"
      yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    some-label: some-label-value
spec:
  containers:
  - name: yarn-build
    image: node:erbium
    command:
    - cat
    tty: true
"""
    }
  }
  stages {
    stage("Build") {
      steps {
        sh """
        yarn
        yarn compile
        """
      }
    }
  }
}
