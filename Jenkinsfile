pipeline{
  agent none
  stages{
    stage('build'){
      agent{label 'slaveone'}
      steps{
            sh 'echo ${BUILD_NUMBER}'
            sh 'pwd'
            sh 'mvn package'
            sh 'scp -r target/build-demo-1.0.0.war root@172.31.2.54:/opt/tomcat/webapps'
            echo "package build successfully and copied"
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
