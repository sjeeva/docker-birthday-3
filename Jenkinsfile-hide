node ('docker') {
  stage "Checkout App"
  checkout scm
  
  dir ('example-voting-app') {
    stage "Build Images"
    sh "docker-compose -p automation -f docker-compose.yml build"

    stage "Deploy Application"
    sh "docker-compose -p automation -f docker-compose.yml -f docker-compose.singlenode.yml stop"
    sh "docker-compose -p automation -f docker-compose.yml -f docker-compose.singlenode.yml rm -f"
    sh "docker-compose -p automation -f docker-compose.yml -f docker-compose.singlenode.yml up -d"

    stage "Publish Application Details"
    sh "docker-compose -p automation -f docker-compose.yml -f docker-compose.singlenode.yml ps"
  }
}
