



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
        stage('Deployment_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativepipelineWithSharedlibraries","172.31.29.234","testapp")
                }
            }
        }

        stage('Testing_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativepipelineWithSharedlibraries")
                }
            }
        }
        stage('Delivery_Mater')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativepipelineWithSharedlibraries","172.31.19.221","prodapp")
                }
            }
        }
    }
}
