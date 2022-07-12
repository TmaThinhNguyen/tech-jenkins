pipeline{
    agent any
    parameters{
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0' ],  description: '')
        booleanParam(name: 'excuteTests', defaultValue: true, description: '')
    }
    stages{
        stage('build'){
            steps{
                echo "building the application..."
                echo "building version ${NEW_VERSION}"
            }
        }
        stage('test'){
            steps{
                echo "test the application..."
                when{
                    expression{
                        param.excuteTests
                    }
                }
            }
        }
        stage('deploy'){
            steps{
                echo "deploy the application..."
                echo "deploying version ${VERSION}" 
            }
        }
    }
}