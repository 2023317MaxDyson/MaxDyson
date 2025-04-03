pipeline{
agent only
    stages{
       stage('Build'){
       agent{
         docker{
            image '22.11.0-bullseye'
            reuseNode true
         }
       }
         steps{
            sh '''
            ls -la
            node --version
            npm --version
            npm install
            npm run build
            ls -la
            '''
         }
     }
     stage('Test'){
       agent{
         docker{
            image '22.11.0-bullseye'
            reuseNode true
         }
       }
         steps{
            sh '''
            test -f build/index.html
            npm text
         
            '''
         }
     }
  }
}

