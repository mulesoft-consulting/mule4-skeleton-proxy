# mule4-skeleton-proxy
This is a Mule 4.1 example of an API proxy using API Management that can be used as a starting point for building proxy applications in Mule 4.1. 

Note, the scope features of minimal-logging are not displayed correctly by Studio 7.1 or 7.2. Support for displaying SDK connector scopes is expected in Studio 7.3.

## Uses

The project contains examples using:

* The minimal-logging connector, 
* The secure property connector (formally called the secure-property-placeholder),
* Maven deployment using the mule-maven-plugin descriptor,
* Api Manager gateway auto-discovery registration,
* DataWeave to add values to the minimal-logging transaction properties,
* Mule http proxy extension.

## Purpose

This project is an example, but it can also be used with property configuration changes as a proxy for an API. 

### Configuration Properties

The configuration properties are stored in the src/main/resources-filtered/mule4-skeleton-proxy-${mule.env}.yaml file:

* api.id contains the Api Manager instance's autodiscovery api id,
* proxy.path is the base uri for the proxy, the default is "/",
* proxy.port is the port number of the Api's HTTP listener,
* proxy.responseTimeout is the number of milliseconds the proxy will wait for the implementation to respond,
* implementation.host is the host (ip or host name) where the implementation is deployed,
* implementation.port is the port where the implementation listens for requests,
* implementation.path is the base uri for the implementation,
* implementation.protocol is one of HTTPS or HTTP.

Note that the proxy.port is not used if a shared domain is configured and used for the HTTP listener configuration.

## Runtime properties

The properties mule.env and mule.key need to be set in the Mule runtime in order for the property configurations to be located. Additionally, if the Mule runtime is not configured to connect to API Manager, the API will be disabled (by default).

For Studio, add the following VM command line values when running the API:

 -Danypoint.platform.gatekeeper=disabled -Dmule.env=local -Dmule.key=Mulesoft12345678

## Maven Settingss

The Mule deployment assumes that certain deployment properties will come from profiles specified when the mvn command is executed. An example-settings.xml is provided as a reference
for creating your own settings.xml file. This is a standard feature of Maven and is described in its online documentation. Once the settings.xml file has been created, export a u and a p shell environment variables containing your Anypoint user name and password. Then use this maven command to deploy the API project:

```
mvn clean install deploy -Denv=xxx -DmuleDeploy
```
Replacing the xxx's with the appropriate values.
