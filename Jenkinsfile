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
            steps{
                echo 'stage B'
                script{
                if(isA){
                    echo 'stage B is Running'
                }
                }
            }
        }

        stage('C'){
            steps{
                echo 'stage C'
                script{
                if(!isA){
                    echo 'stage C is Running'
                }
                }
            }
        }
    }
}
