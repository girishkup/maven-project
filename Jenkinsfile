pipeline
{

agent {
  label 'DevServer'
}

parameters {
  string defaultValue: 'upadhyay', name: 'LASTNAME'
}

environment{
  NAME = "girish"
}
tools {
  maven 'mymaven'
}

stages{

    stage('build')
    {
        steps{
            sh 'mvn clean package'
            echo "hello $NAME  ${params.LASTNAME}"
        }

        post {
        success {
            archiveArtifacts artifacts: '**/target/*.war'
                }
            }  
    }

}

}