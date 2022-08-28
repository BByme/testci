pipeline {
    
    agent any 
    parameters {
        string(name: 'repo_url', description: 'URL de repo GIT', defaultValue: 'https://github.com/BByme/testci.git')
        string(name: 'repo_branch', description: 'Branch GIT', defaultValue: 'master')
    }
        stages{

        stage("Checkut"){
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: "*/${params.repo_branch}"]],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[ $class: 'LocalBranch',localBranch: params.repo_branch]],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: params.repo_url, credentialsId: 'MY_GITHUB_ACCOUNT_01']]
                ])
                script {
                    sh 'echo HelloWorld'
                }
            }
        }    

       } 
    
}
