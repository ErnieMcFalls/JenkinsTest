pipeline {
  agent any
  stages {
    stage('One'){
      steps{
        echo "Step one engaged"
      }
    }
    stage('Two'){
      steps{
        input('Do you want to proceed to the next step')
      }
    }
    stage('Three'){
      when{
        not{
          branch "main"
        }
      }
      steps{
        echo "boy"
      }
    }
    stage('Four'){
      parallel{
        stage('Unit Test'){
          steps{
            echo "Running the unit test..."
          }
        }
        stage('Integration Test'){
          agent{
            docker{
              reuseNode false
              image 'ubuntu'
            }
          }
          steps{
            echo "Running the integration test..."
          }
        }
      }
    }
  }
}

              
