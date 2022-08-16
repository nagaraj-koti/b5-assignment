boolean isA=true
pipeline{
    agent any
    stages{
        stage('A'){
            steps{
            try{
                echo 'Stage A is Running'
            }catch(Exception e){
                echo 'Stage A Failed'
                isA=false
            }
        }
        }

        stage('B'){
            steps{
                if(isA){
                    echo 'stage B is Running'
                }
            }
        }

        stage('C'){
            steps{
                if(!isA){
                    echo 'stage B is Running'
                }
            }
        }
    }
}