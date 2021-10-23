pipeline {
    agent none
      stages {
          stage('PnemoniaDetectionMlops'){
              agent {
                label 'kubernetes_master'
            }
                steps {
                    sh 'sudo kubectl create deployment pnemoniadetectpod  --image=sathya15/pneumonia_detection:v2' 
                    sh 'sudo kubectl expose deployment pnemoniadetectpod --type=NodePort  --port=4444'
                    sh 'sudo kubectl get pod -o wide'
                    
                }
        }
         stage('gettingpod'){ 
             agent {
                label 'kubernetes_master'
            }
               steps {
                      sh 'sudo kubectl get pod -o wide '
                      sh 'sudo kubectl get svc'
             }
        }
    }
}
