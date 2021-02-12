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
}

}
