pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build_trusty_python2_library') {
          steps {
            awsCodeBuild envVariables: '[ { RUN_TESTS, false } ]', projectName: 'build_trusty_python2_library', region: 'us-east-1', sourceControlType: 'jenkins', credentialsType: 'keys'
          }
        }
        stage('build_bionic_python2_library') {
          steps {
            awsCodeBuild envVariables: '[ { RUN_TESTS, false } ]', projectName: 'build_bionic_python2_library', region: 'us-east-1', sourceControlType: 'jenkins', credentialsType: 'keys'
          }
        }
      }
    }
  }
}
