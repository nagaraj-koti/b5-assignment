boolean isA=true
pipeline{
    agent any
    stages{
        stage('A'){
            steps{
                echo 'stage A'
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
<<<<<<< HEAD
                echo 'Stage B is running'
=======
                echo 'stage B'
                script{
                if(isA){
                    echo 'stage B is Running'
                }
                }
>>>>>>> fed6e637df1ffdb331a0c2e8e278cc04e839fd3e
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
