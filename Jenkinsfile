pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/aena1236456/GitOps- will replace by sed command before RUN
        git url: 'https://github.com/aena1236456/GitOps-', branch: 'main'
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