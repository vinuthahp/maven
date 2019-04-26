node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Checkout code from repository
   checkout scm

   // Get the maven tool.
   // ** NOTE: This 'M2' maven tool must be configured
   // **       in the global configuration.
   def mvnHome = tool 'M2'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   bat "C:\Program Files\maven\bin\mvn clean install"
}
