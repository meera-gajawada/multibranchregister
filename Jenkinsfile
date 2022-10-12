def appName='devops-sample-app'
def changesetNumber='Chset-19'
def snapshotName =null
def changeSetRegResult=''
def changeSetResults=''
pipeline {
   agent any
   stages {
   /*     stage("Clone Repo"){
          steps{
            echo "testing the multibranch configuration in main branch"
          
          }
        }
        stage('Branch-Fix* Steps') {

          when {

            branch "fix-*"

          }

          steps {
              echo "this is from branch fix-*"

          }

        }
        stage('Register for test1') {

          when {

            branch "test1*"

          }

          steps {
            script{
              changeSetResults = snDevOpsConfigGetSnapshots(
                applicationName: "${appName}",
                changesetNumber: "",
                deployableName: "Development_1",
                outputFormat:"xml",
                isValidated:false,
                showResults:false,
                markFailed:false
              )
              
              echo"################# ChangeSetResult:=\n${changeSetResults}"

              if (changeSetResults !=null){
                def changeSetResultsObject = readJSON text: changeSetResults
                changeSetResultsObject.each {
                  snapshotName = it.name
                }
              }

              echo"################# Snapshot going to be registered:= ${snapshotName}"
              sleep 10
              changeSetRegResult = snDevOpsConfigRegisterPipeline(
                applicationName:"${appName}",
                // changesetNumber:"${changesetNumber}"
                snapshotName:"${snapshotName}"
                ,showResults:true
              )

              echo"################# Registration result:=${changeSetRegResult}"

            }
          }

        }
        stage('Register for main ') {

          when {

            branch "main*"

          }

          steps {
            script{
              changeSetResults = snDevOpsConfigGetSnapshots(
                applicationName: "${appName}",
                changesetNumber: "",
                deployableName: "Production_1",
                outputFormat:"xml",
                isValidated:false,
                showResults:false,
                markFailed:false
              )
              
              echo"################# ChangeSetResult:=\n${changeSetResults}"

              if (changeSetResults !=null){
                def changeSetResultsObject = readJSON text: changeSetResults
                changeSetResultsObject.each {
                  snapshotName = it.name
                }
              }

              echo"################# Snapshot going to be registered:= ${snapshotName}"
            
              changeSetRegResult = snDevOpsConfigRegisterPipeline(
                applicationName:"${appName}",
                snapshotName:"${snapshotName}"
                ,showResults:true
              )

              echo"################# Registration result:=${changeSetRegResult}"

            }
          }

        }
        stage('Register for Test2') {

          when {

            branch "test2*"

          }

          steps {
            script{
              changeSetResults = snDevOpsConfigGetSnapshots(
                applicationName: "${appName}",
                changesetNumber: "",
                deployableName: "Production_1",
                outputFormat:"xml",
                isValidated:false,
                showResults:false,
                markFailed:false
              )
              
              echo"################# ChangeSetResult:=\n${changeSetResults}"

              if (changeSetResults !=null){
                def changeSetResultsObject = readJSON text: changeSetResults
                changeSetResultsObject.each {
                  snapshotName = it.name
                }
              }

              echo"################# Snapshot going to be registered:= ${snapshotName}"
            
              changeSetRegResult = snDevOpsConfigRegisterPipeline(
                applicationName:"${appName}",
                snapshotName:"${snapshotName}"
                ,showResults:true
              )

              echo"################# Registration result:=${changeSetRegResult}"

            }
          }

        }


        stage("Register pipeline using Changeset"){
          steps{
              echo "################# Registering pipeline again using changesetNumber:${changesetNumber}"
              script{
                sleep 5
                changeSetRegResult = snDevOpsConfigRegisterPipeline(
                        applicationName:"${appName}",
                        changesetNumber:"${changesetNumber}"
                        //,snapshotName:"${snapshotName}"
                        ,showResults:true)

                echo "################# Pipeline registration result: ${changeSetRegResult}"  
                
              }
          }
        }
        stage("Initiate ChangeRequest"){
            steps{
                echo "Initating change request for APPLICATION:=${appName} for SNAPSHOT:=${snapshotName}"
                script{
                  if(snapshotName != null){
                    echo"################# Creating CR with AppName:=${appName} and SnapName:=${snapshotName}"
                    // changeSetCreateResult = snDevOpsChange(
                    //   applicationName:"${appName}",
                    //   snapshotName:"${snapshotName}"
                    // )
                  }else{
                    echo"################# Creating generic CR"
                    // changeSetCreateResult = snDevOpsChange()
                  }
                    
                    // echo "################# CR creation result:=${changeSetCreateResult}"  
                  
                }
            }
        } */
      stage("Register pipeline Test"){
          steps{
              echo "################# Registering pipeline again using snapshotName: Production_1-v14.dpl"
              script{
                sleep 5
                changeSetRegResult = snDevOpsConfigRegisterPipeline(
                        applicationName:"${appName}",
                        snapshotName:"Production_1-v14.dpl"
                        ,showResults:true)



               echo "################# Pipeline registration result: ${changeSetRegResult}"  
                
              }
          }
        }
   }
}
