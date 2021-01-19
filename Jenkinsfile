node {

stage('SCM'){
 git 'https://github.com/Hiennguyenalice/gestionAgenceVoyage'
}

stage('Compile'){
def mvnHome = tool name: 'maven-3' , type: 'maven'
sh "${mvnHome}/bin/mvn package"
}

stage('SonarQube') {
  def mvnHome = tool name: 'maven-3' , type: 'maven'
  export SONAR_TOKEN="2070c7658740d71f70521371f3a4ae13290a9433"
  sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://192.168.1.64:9000/ -Dsonar.login=$SONAR_TOKEN"
    }
}
