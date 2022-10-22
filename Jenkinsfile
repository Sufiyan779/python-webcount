pipeline{
    agent {label 'OPENJDK-11-4'}
   
 stages{
    stage('pull from vcs') {
        steps{
            git url: 'https://github.com/Sufiyan779/python-webcount.git',
            branch: 'python'
        }

    }
    stage('archive result'){
        steps{
            junit '**junit-py39.xml'
        }

    }
     stage('artifacts'){
        steps{
            archiveArtifacts artifacts: '**/webcount-0.1.zip'
        }
        
    }
 }   
}