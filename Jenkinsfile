node ('master'){
def server = Artifactory.server "jfrog"
def buildInfo = Artifactory.newBuildInfo()

stage('Download Package') {
   def downloadSpec = """{ 
     "files": [
       {
        "pattern": "generic-local/*.war",
         "target": "files/"
       }
      ]
   }"""
   server.download spec: downloadSpec
 }

stage('Deploying to stage server') {
deploy adapters: [tomcat8(credentialsId: 'edd0013c-d2fc-4ceb-9acb-db1689b2cc1b', path: '', url: 'http://34.68.249.66:8081/')], contextPath: null, war: '**/*.war'
}

}
