# Steps to deploy on Openshift


>>> Import fuse image 

oc import-image fuse7/fuse-java-openshift --from=registry.access.redhat.com/fuse7/fuse-java-openshift --confirm

>>> Create a new build 

oc new-build --binary=true --image-stream=fuse-java-openshift  --name=cameltokafka

>>> Start the build pointing the -from-dir parameter to the amq-streams-camel project folder.

oc start-build cameltokafka --from-dir=. --follow

>>> Create a new app 

oc new-app cameltokafka


