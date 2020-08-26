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
