boolean isA=true
pipeline{
    agent any
    stages{
        stage('A'){
            steps{
            script{
                try{
                echo 'Stage A is Running'
                sh 'exit 1'
            }catch(Exception e){
                echo 'Stage A Failed'
                isA=false
            }
            }
        }
        }

        stage('B'){
            when {
                expression {
                    isA == true
                }
            }
            steps{
                echo 'Stage B is running'
            }
        }

        stage('C'){
            when {
                expression {
                    isA == false
                }
            }
            steps{
                echo 'Stage C is running'
            }
        }
    }
}