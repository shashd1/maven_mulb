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
       
       }
    }
