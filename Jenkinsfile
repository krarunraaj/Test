#!/usr/bin/env groovy
properties([
  parameters([
    string(name: 'Branch', defaultValue: 'master', description: 'The target environment' ),
    file(name: 'filePath', defaultValue: 'TESTING', description: 'Input excel file location in git' ),
    string(name: 'jar', defaultValue: 'JAR', description: 'Executable jar location in git' )
   ])
])


timestamps{
       node('master'){
            try{
                deleteDir()
                stage('Checkout SCM'){
                    checkout scm
                 
                }

                stage('Download excel'){
                  echo env.filePath
                  
                   def filedata = null
    def filename = null
 

    // Read contents and write to workspace
    writeFile(file: filename, encoding: 'Base64', text: env.filePath.read().getBytes().encodeBase64().toString())
    // Remove the file from the master to avoid stuff like secret leakage
   
                               

                }

                stage('Download jar'){
                    script
                            {
                              //  sh "wget -O utility.jar  ${IMPORT_JAR}"
                            }
                }

                stage('Execute utility to upload'){
                    script
                            {
                              //  sh "java -jar  utility.jar -O inputexcel.xls"
                            }

                }





              //  currentBuild.result='SUCCESS'

            } catch (err){

                throw err
            }
        
    }
}
