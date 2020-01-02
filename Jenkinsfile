junit '**/target/failsafe-reports/TEST-*.xml'
       archive 'target/*.jar'
     }
     stage ('Publish'){
       def server = Artifactory.server 'Default Artifactory Server'
       def uploadSpec = """{
"files": [ {
             "pattern": "target/hello-0.0.1.war",
             "target": "example-project/${BUILD_NUMBER}/",
             "props": "Integration-Tested=Yes;Performance-Tested=No"
} ]
}"""
       server.upload(uploadSpec)
     }
}
