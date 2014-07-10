SSH mirror maven configuration
==============================

This project contains a sample pom.xml and settings.xml for use with the DTG's ssh maven mirror sftp://maven@maven.dtg.cl.cam.ac.uk/mirror/

To access it you will need a verified [monkeysphere enabled GPG key](http://web.monkeysphere.info/getting-started-ssh/#index1h1) with the [uid registered with the server](https://github.com/ucam-cl-dtg/dtg-puppet/blob/master/manifests/nodes/code.pp).

To get your key verified you need to talk to Daniel Thomas (drt24) or Oliver Chick (oc243).

This will give you read only access, if you want write access you will need to access the http mirror from inside the DTG network with the relevant credentials.

Setup
-----

From the pom.xml file the important thing is the wagon-ssh extension which you need to include in the pom of the project you want to build.

From the settings.xml you need to add all the content to your existing settings.xml, or if you don't have one then you can just add this.
The first time you build a project which depends on the repository you will need to leave the commented out section commented out, later you can choose to uncomment it as this will mean you will use our local cache rather than hitting the central mirrors.
