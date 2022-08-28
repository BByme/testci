pipeline {
    
    agent any 
    parameters {
        string(name: 'repo_url', description,'URL de repo GIT', defaultValue: 'https://github.com/BByme/testci.git')
        string(name: 'repo_branch', description, 'Branch GIT', defaultValue: 'master')
    }
        stages{

        stage("Checkut"){
            steps{
                checkout()    
            }
        }    

       } 
    
}
