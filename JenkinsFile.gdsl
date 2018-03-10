pipeline {
    agent any
    tools { 
        maven 'm3' 
    }
    stages {
        stage ('Initialize') {
            steps {
               git 'E:/drive/info/Projets/github/effectiveJava3'
               sh "git clean -f && git reset --hard origin/master"      
            }
        }

        stage ('Build') {
            steps {
                script { 
                   sh "ls -l > commandResult"
                   def result = readFile('commandResult').trim()
                   echo result
                   build job: 'projet.git', parameters: [string(name: 'key1', value: "${result}")]
                }
            }
        }
    }
    
}