#!/usr/bin/env groovy
properties([
  parameters([
    string(name: 'Branch', defaultValue: 'master', description: 'The target environment' ),
    file(name: 'filePath', defaultValue: 'TESTING', description: 'Input excel file location in git' ),
    string(name: 'jar', defaultValue: 'JAR', description: 'Executable jar location in git' )
   ])
])

def label = "TT-reference-upload-${UUID.randomUUID().toString()}"
timestamps{
       node(label){
            try{

                stage('Checkout SCM'){
                    checkout scm
                    // install jq here, we need in C1 cleanup
                    env.PATH = "/usr/bin/jq:${env.PATH}"
                    sh "chmod a+x lib/jq-linux64"
                    sh "cp lib/jq-linux64 /usr/bin/jq"
                }

                stage('Download excel'){

                                script
                                        {
                                          sh "wget -O inputexcel.xls ${IMPORT_DATA_URL}"
                                        }

                }

                stage('Download jar'){
                    script
                            {
                                sh "wget -O utility.jar  ${IMPORT_JAR}"
                            }
                }

                stage('Execute utility to upload'){
                    script
                            {
                                sh "java -jar  utility.jar -O inputexcel.xls"
                            }

                }





                currentBuild.result='SUCCESS'

            } catch (err){

                throw err
            }
        }
    }
}
