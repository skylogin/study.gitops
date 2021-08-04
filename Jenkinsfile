pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/skylogin/study.gitops will replace by sed command before RUN
        git url: 'https://github.com/skylogin/study.gitops', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}