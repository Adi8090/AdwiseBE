pipeline{
  agent any 
   stages{
    stage('Git Checkout'){
     steps{
            git 'https://github.com/Adi8090/AdwiseBE'
         }               
     }
    stage('java build'){
     steps{
             sh '/opt/maven/bin/mvn clean deploy -Dmaven.test.skip=true'
     }
    }
    stage('Run'){
        steps{
             sh 'export JENKINS_NODE_COOKIE=dontkillme ;nohup java -jar $WORKSPACE/target/*.jar &'
        }
    }
   }
}
