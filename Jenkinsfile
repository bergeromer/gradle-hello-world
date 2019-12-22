node {

  def gradleHome = tool 'gradle4'

  stage('checkout'){
      checkout scm
  }

  stage('build') {
      sh "${gradleHome}/bin/gradle build"
  }
  
  stage('badge') {
      echo "succeeded"
      addInfoBadge("finished")
  }
}
