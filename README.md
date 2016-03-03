#OpenVIVO custom installer
This is a git repository for [VIVO](http://vivoweb.org/) customizations pertaining to the [OpenVIVO](https://github.com/openvivo) project. Local themes, extensions, and core overrides go here.

##Building the application

Assuming that the VIVO, Vitro, and openvivo-installer projects are in the same directory.

###Develop branch
~~~

#Copy default developer.properties, runtime.properties, applicationSetup.n3

  cp example.developer.properties developer.properties
  cp example.runtime.properties runtime.properties
  cp example.applicationSetup.n3 applicationSetup.n3

#Adjust developer, runtime, and applicationSetup properties
#Create the openvivo data directory specified in openvivo-settings.xml if it doesn't exist. Eg:

  mkdir -p /usr/local/openvivo/data/config
  cp runtime.properties /usr/local/openvivo/data
  cp applicationSetup.n3 /usr/local/openvivo/data/config
  cp developer.properties /usr/local/openvivo/data/config

#Build and deploy VIVO

  cd ../VIVO
  mvn clean install -s ../openvivo-installer/openvivo-settings.xml -Dvivo-installer-dir=../openvivo-installer

~~~
