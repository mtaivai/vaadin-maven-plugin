The documentation for the **GWT Maven Plugin** is here: http://mojo.codehaus.org/gwt-maven-plugin/

[![Build Status](https://buildhive.cloudbees.com/job/gwt-maven-plugin/job/gwt-maven-plugin/badge/icon)](https://buildhive.cloudbees.com/job/gwt-maven-plugin/job/gwt-maven-plugin/)

Note for the Arcusys branches:
 - These are not official builds and you can skip certain tasks:
   - gpg signing
   - tests (!)
   - enforcer
 - We deploy to Arcusys Maven repositories arcusys-oss-snapshots and arcusys-oss-releases

 - The plugin is available in repository
   https://dev-1.arcusys.fi/mvn/content/groups/public

How to skip above mentioned QA tasks? 
  
Define a profile in your ~/.m2/settings.xml:
  
	<profile>
		<id>dev-vaadin-maven-plugin</id>
		<activation><activeByDefault>true</activeByDefault></activation>
		<properties>
			<gpg.passphrase.file>/dev/null</gpg.passphrase.file>
			<skipTests>true</skipTests>
			<enforcer.skip>true</enforcer.skip>
			<gpg.skip>true</gpg.skip>
			<altDeploymentRepository>arcusys-oss-snapshots::default::https://dev-1.arcusys.fi/mvn/content/repositories/arcusys-oss-snapshots</altDeploymentRepository>
		</properties>
	</profile>
