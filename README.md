# Ansible Role for installing Oracle JDK on RHEL

This role installs the Oracle JDK from Red Hat package repos, uses Alternatives to set it as default, and 
applies the JCE policy fix.
 
This has been tested on RHEL6 with Java packages for versions 1.7.0 and 1.8.0.  
 
In order to apply the JCE policy fix you need to download a copy of the Oracle JCE Unlimited Strength Jurisdiction 
Policy extensions and place the US_export_policy.jar and local_policy.jar files into your files directory. 
 
The policy extension files should be renamed according to the java version you're installing in order for the role to 
support multiple versions. For example:
 
    files/US_export_policy-1.8.0.jar
    files/local_policy-1.8.0.jar
    
You can download the JCE extensions from the Oracle website here:

**Java 1.8**
    
    http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html

**Java 1.7** 
    
    http://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html
 

# Requirements

1. A Redhat server. This role has only been tested with RHEL6. Requires the Red Hat licensed RPM repos. 

# Variables

As defined in defaults (can be overridden):
    
    oracle_java_version: 1.8.0 