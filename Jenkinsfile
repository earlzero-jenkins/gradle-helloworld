node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get some code from a GitHub repository
   checkout scm
   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def gradleHome = tool 'gradle'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${gradleHome}/bin/gradle clean test"
   step([$class: 'JUnitResultArchiver', testResults: '**/test-results/TEST-*.xml'])
}
