pipeline {
    
    agent any 
    parameters {
        string(name: 'repo_url', description: 'URL de repo GIT', defaultValue: 'https://github.com/BByme/testci.git')
        string(name: 'repo_branch', description: 'Branch GIT', defaultValue: 'master')
    }
        stages{

        stage("Checkut"){
            
            environment {
                M2_HOME = tool 'MAVEN'
                JAVA_HOME = tool 'JAVA_8'
                PATH = "${env.JAVA_HOME}/bin:${env.M2_HOME}"
            }
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: "*/${params.repo_branch}"]],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[ $class: 'LocalBranch',localBranch: params.repo_branch]],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: params.repo_url, credentialsId: 'MY_GITHUB_ACCOUNT_01']]
                ])
                
                sh 'echo HelloWorld'
                mvn -version
                java -version

            }
        }    

       } 
    
}
