# 참고

# 이전 파이프라인
```
pipeline {
    agent any
    tools {
        jdk "javaJDK"
         maven 'M2_HOME'
     }
    stages {
        stage('Checkout'){
          steps{
            script {
                println('========== Checkout ========== ')
                git credentialsId:'giteaToken', url:'http://192.168.110.99:3000/hanssem/invoicetax.git', branch:'barobill'
               }
            }
          }
          
    }

}
```
