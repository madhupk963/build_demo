pipeline{
  agent none
  stages{
    stage('build'){
      agent{label 'slaveone'}
      steps{
            sh 'pwd'
            sh 'mvn package'
            echo "package build successfully"
      }
    }
    stage('deploy'){
      agent{label 'slavetwo'}
      steps{
        sh 'sudo sh /opt/tomcat/bin/startup.sh'
      }
    }
  }
}
