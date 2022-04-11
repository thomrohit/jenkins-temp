pipeline {
    agent any
triggers {
  pollSCM '* * * * *'
}
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                checkout([$class: 'PlasticSCM', cleanup: 'MINIMAL', credentialsId: 'github_token_as_password', directory: '', pollOnController: true, selector: '''repository "jenkins-temp@Goals@cloud"
  path "/"
    smartbranch "/main"''', useMultipleWorkspaces: false, workingMode: 'NONE'])
            }
        }
    }
}
