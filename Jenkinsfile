node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Checkout code from repository
   checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '8f2a8854-a62a-4778-be78-b18d2a60d7ea', url: 'https://github.com/selvajitheone/sim-maven-proj.git']]]

   // Get the maven tool.
   // ** NOTE: This 'M2' maven tool must be configured
   // **       in the global configuration.
   def mvnHome = tool 'M2'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   bat '%MVN_HOME%\\bin\\ mvn clean install'
}
