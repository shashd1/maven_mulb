@Library('mylib')_
pipeline
{
    agent any
    stages
    {
        stage('conDown_master')
        {
            steps
            {
                script
                {
                    cicd.gitDown("maven") 
                }
            }
        }
        
        stage('ConBuild_master')
        {
             steps
             {
                script
                {
                  cicd.mavenbuild()
                }
              }    
         
        }
        
        stage('ConDeploy_master')
        {
            steps
            {
                script
                {
                    cicd.tomdeploy("DeclarativePipelineSrdlib","172.31.39.155","testapp")
                }
            }
        }
        
        stage('ConTest_master')
        {
            steps
            {
                script
                {
                    cicd.gitDown("FunctionalTesting")
                    cicd.runselinium("DeclarativePipelineSrdlib")
                }
            }
        }
        
        stage('ConDelv_master')
        {
            steps
            {
                script
                {
                    cicd.tomdeploy("DeclarativePipelineSrdlib","172.31.33.88","prodapp")
                }
            }
        }
    }    
}
