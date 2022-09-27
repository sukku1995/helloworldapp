pipeline{
    agent{
        label{
            label "ubuntu-slave"
        }
    }
    tools{
        maven "M2_HOME"
    }
    stages{
        
        stage('Git'){
            steps{
            checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: '6f7f5bba-61d5-45e4-82fa-4cf295e7dec9', url: 'https://github.com/muralikrishna188/helloworldapp.git']]]
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
        }
    }
}
