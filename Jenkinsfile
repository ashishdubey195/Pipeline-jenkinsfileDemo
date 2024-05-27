pipeline{
    
    tools{
        maven 'mymaven'
    }
    
   agent any
   
   parameters{
       
       choice(name: "ENV",choices: ["","Dev","QA"])
       
   }
    
    stages{
        
        stage('Build in Dev Env')
        {
            when { expression { params.ENV == 'Dev' } }
            steps{
                  git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
                  sh 'mvn pmd:pmd'
                  sh 'mvn package'
            }
        }
        
         stage('Build in Test Env')
        {
            when { expression { params.ENV == 'QA' } }
            steps{
                  git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
                  sh 'mvn test'
                  sh 'mvn package'
            }
        }

        
        
        
    }
    
    
    
}
