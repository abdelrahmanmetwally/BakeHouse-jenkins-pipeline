pipeline {
    agent {label 'smart-village'}

    stages {
      
        stage('build') {            
            steps {
                echo 'build'
                script {
//                   if (BRANCH_NAME == "dev" || BRANCH_NAME == "test" || BRANCH_NAME == "preprod") {
                  withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'USERNAME_iti', passwordVariable: 'PASSWORD_iti')]) {
                            sh '''
                            docker login -u ${USERNAME_iti} -p ${PASSWORD_iti}
                               
                                docker build -t  abdo23/bakehouseiti:v${BUILD_NUMBER} .                             
                                docker push  abdo23/bakehouseiti:v${BUILD_NUMBER}
//                                echo ${BUILD_NUMBER} > ../build.txt
                                                              

                                '''
                          }
                     }
//                         else {  echo "choosen branch ${BRANCH_NAME}"}
                    
//                 }            
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy'
//                  script {
//                            if (BRANCH_NAME == "release") {
//                         withCredentials([file(credentialsId: 'file-iti-credentials', variable: 'KUBECONFIG_file')]) {
//                             sh '''
                                         echo 'hello'
//                                 export ${BUILD_NUMBER} = $(cat ../build.txt)
//                                 mv Deployment/deploy.yaml Deployment/deploy.yaml.tmp
//                                 cat Deployment/deploy.yaml.tmp | envsubst > Deployment/deploy.yaml
//                                 rm -f Deployment/deploy.yaml.tmp
//                                 kubectl apply -f Deployment --kubeconfig ${KUBECONFIG_file} -n ${BRANCH_NAME}
//                             '''
//                          }
//                         }
//                 }
              }
        }
    }
}
