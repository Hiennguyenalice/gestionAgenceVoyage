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
  sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://192.168.1.64:9000/ -Dsonar.login=7deeeca30c167968d4b94e2b7189cdca64cd61d1"
    }
}
