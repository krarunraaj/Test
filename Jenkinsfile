properties([
  parameters([
    string(name: 'DEPLOY_ENV', defaultValue: 'TESTING', description: 'The target environment', )
   ])
])


pipeline {
   agent any
   
   stages {
       
     stage('Validate')
     {
       steps
       {
         script 
         {
        def inputFile = input message: 'Upload file', parameters: [file(name: 'data.zip')]
        new hudson.FilePath(new File("$workspace/data.zip")).copyFrom(inputFile)
        inputFile.delete()
     }
       }
     }
     
     
      /*  stage('EnterUserInput') {
         steps {
             script {
                 
                 def userInputTxt = input(
                                     id: 'inputTextbox', message: 'Please enter JOB Description', parameters: [
                                     [$class: 'TextParameterDefinition', description: 'String or Integer etc..',name: 'input']
                                    ])
                    echo ("JOB Description is: ${userInputTxt}")
                     
             }}   
        }
        
         stage('Upload a CSV') {
         steps {
             script {
                 
                        def inputCSVPath = input message: 'Upload file', parameters: [file(name: 'Test.csv', description: 'Upload only CSV file')]
                        def csvContent = readFile "${inputCSVPath}"
                        
                         echo ("CSV FILE PATH IS : ${inputCSVPath}")
                         echo("CSV CONTENT IS: ${csvContent}") 
        }
                 
                 echo env.STAGE_NAME
                 echo '=========== Upload a CSV =============='
                
                        
         }
      }
    */   
   }
  }
