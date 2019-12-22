node ('slave1') {

  def gradleHome = tool 'gradle4'

  stage('checkout'){
      git url: 'https://github.com/otomato-gh/gradle-hello-world', branch : ‘master’
  }

  stage('build') {
      sh "${GRADLE_HOME}/bin/gradle build"
  }
  
  stage('badge') {
      echo "succeeded"
      addInfoBadge("finished")
  }
}
