



@Library('mylibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Download_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload('maven2')
                }
            }
        }
        stage ('Build_Master')
        {
            steps
            {
               script
               {
                cicd.buildArtifact()
                }
            }
        }
      }
    }
