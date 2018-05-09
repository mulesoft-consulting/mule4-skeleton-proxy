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


