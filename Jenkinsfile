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
  }
}
