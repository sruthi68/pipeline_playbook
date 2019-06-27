node {
    try {
        stage('Checkout') {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sruthi68/playbook.git']]])
        }
        stage('Syntax check for playbook') {
            sh 'ansible-playbook --syntax-check ./sampleFile.yml'
        }
        stage('Check for playbook') {
            sh 'ansible-playbook --check ./sampleFile.yml'
        }
        stage('Execute playbook') {
            sh 'ansible-playbook samplFile.yml'
        }
        stage('Pipeline status') {
            echo "Pipeline status: ${currentBuild.currentResult}"   
        }
    }
    catch (Exception err) {
          echo "Pipeline status: ${currentBuild.currentResult}"   
    }
}
