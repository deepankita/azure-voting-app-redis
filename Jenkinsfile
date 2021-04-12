pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
       stage('Docker Build') {
         steps {
            powershell( 'Docker images -a')
            powershell( """
               cd azure-vote/
               Docker images -a
               Docker build -t jenkins-pipeline .
               Docker images -a
               cd ..
            """)
         }
      }
   }
}
     
