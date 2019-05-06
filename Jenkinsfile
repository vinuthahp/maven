node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Checkout code from repository
   checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '8f2a8854-a62a-4778-be78-b18d2a60d7ea', url: 'https://github.com/selvajitheone/sim-maven-proj.git']]]

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.
   //def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   bat 'mvn clean install'
   
   //Deploy
   stage 'Deploy'
   //Run command to deploy war file
   powershell 'remove-item "D:\\devops-tools\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps\\sim-mvn-proj.war"'
   powershell 'mv "C:\\Program Files (x86)\\Jenkins\\workspace\\*ltiBranch-Project-01_master-*\\target\\*.war" "D:\\devops-tools\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps\\sim-mvn-proj-Master.war"'
   powershell 'mv "C:\\Program Files (x86)\\Jenkins\\workspace\\*ltiBranch-Project-01_dev-*\\target\\*.war" "D:\\devops-tools\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps\\sim-mvn-proj-dev.war"'
   powershell 'mv "C:\\Program Files (x86)\\Jenkins\\workspace\\*ltiBranch-Project-01_test-*\\target\\*.war" "D:\\devops-tools\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps\\sim-mvn-proj-test.war"'
}
