Tomcat7 (with Websockets) on Red Hat's OpenShift PaaS
=====================================================

Tomcat7 running on OpenShift with Websocket support.

This git repository is a sample application to help you get started
with using Tomcat7 on Red Hat's OpenShift PaaS.


Steps to get Tomcat7 running on OpenShift
-----------------------------------------

Create an account at http://openshift.redhat.com/

Create a namespace, if you haven't already do so

    rhc domain create -n <yournamespace>

Create a diy-0.1 application (you can name it anything via -a)

    rhc app create tomcat7 diy-0.1


Add this `github openshift-tomcat7-websockets` repository

    cd tomcat7
    git remote add upstream -m master git@github.com:ramr/openshift-tomcat7-websockets.git
    git pull -s recursive -X theirs upstream master
    
Then push the repo to OpenShift

    git push

That's it, you can now checkout your application on either of the
experimental websocket enabled ports:

    http://tomcat7-$yournamespace.rhcloud.com:8000
    OR
    https://tomcat7-$yournamespace.rhcloud.com:8443


