node {
  def app

  stage("Clone repository") {
        checkout scm
  }

   stage("Build image") {
        app = docker.build("smokimk/test2")

  }
   stage("Push image"){
     docker.withRegistry('https://registry.hub.docker.com/%27,%27docker%27) { 
       app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
       app.push("${env.BRANCH_NAME}-latest")
     }
  }

}
