# FAQ / Troubleshooting Guide


## Problems? Questions? Suggestions?

Post any problems, questions or suggestions to the Dynatrace Community's [Application Monitoring & UEM Forum](https://answers.dynatrace.com/spaces/146/index.html).
 

## FAQ

##### Dynatrace AppMon version compatibility - which version works with the plugin?
> 6.1 and newer


##### Do I need to use an additional plug-in for Ant, Maven, MS Build to register my tests?

> Not anymore. The registration of the test run is done through the Jenkins Plugin. The test run id ${dtTestrunID} is passed as an environment variable and can be used in your build scripts.

##### Can I use variables to set the version information?

> Build number and jenkins jobs are passed automatically to Dynatrace. Version (major, minor, revision, milestone) currently needs to be set manually (fields are not mandatory). We are looking into allowing the use of variables to set those fields.

## Known Issues

##### SSLHandshakeException when trying to connect through HTTPS

> Dynatrace AppMon Server uses a self-signed certificate per default. Since this certificate doesn't match the URL you are using to access the Server, Jenkins returns an error when trying to connect.

> To solve it:
* either deploy a valid SSL certificate on Dynatrace AppMon server 
* or use the Jenkins plug-in  https://wiki.jenkins-ci.org/display/JENKINS/Skip+Certificate+Check+plugin to skip the certificate check
* or (not recommended) connect through HTTP. In that case, you need to uncheck the setting "Accept authentication data only with HTTPS" under "Dynatrace Server / Services / Management"