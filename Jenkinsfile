node ('docker') {
  stage "Checkout App Code"
  checkout scm
  
  stage "Build Images"
  dir ('example-voting-app') {
    sh "docker-compose -f docker-compose.yml build"
  }
}
