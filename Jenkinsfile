node ('slave1') {

  def gradleHome = tool 'gradle4'
  currentBuild.result = "SUCCESS"
  try {
    stage('checkout'){
        checkout scm
    }

    stage('build') {
        sh "${gradleHome}/bin/gradle build"
    }
  } catch (ex) {
    echo ('Error')
    currentBuild.result = "FAILURE"
  }
  stage ('post') {
    echo "CurrentBuildResult = " + currentBuild.result
    if (currentBuild.result == 'SUCCESS') {
      addBadge(icon: 'green.gif', text:'Build Succeeded')
    }
    if (currentBuild.result == 'FAILURE') {
      addBadge(icon: 'red.gif', text:'Build Failed')
    }
  }
}
