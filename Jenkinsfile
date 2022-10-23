pipeline{
    agent {label 'OPENJDK-11-4'}
   
 stages
 {
    stage('pull from vcs')
    {
        steps
        {
            git url: 'https://github.com/Sufiyan779/python-webcount.git',
            branch: 'python'
        }

    }
    stage('build')
    {
        steps
        {
        sh 'pip3 install -r requirements.txt'
        sh 'tox'
        }

    }
     stage('artifacts')
    {
        steps
        {
            archiveArtifacts artifacts: '.tox/.tmp/package/1/webcount-0.1.zip'
        }
        
    }
    stage('archive result')
    {
        steps
        {
        junit 'junit-py39.xml'
        }

    }
 }
}
    
