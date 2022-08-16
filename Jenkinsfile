boolean isA=true
pipeline{
    agent any
    stages{
        stage('A'){
            steps{
            script{
                try{
                echo 'Stage A is Running'
            }catch(Exception e){
                echo 'Stage A Failed'
                isA=false
            }
            }
        }
        }

        stage('B'){
            steps{
                script{
                if(isA){
                    echo 'stage B is Running'
                }
                }
            }
        }

        stage('C'){
            steps{
                script{
                if(!isA){
                    echo 'stage B is Running'
                }
                }
            }
        }
    }
}