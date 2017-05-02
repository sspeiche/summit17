Setup steps:

First follow setting up the catalog and sample broker https://github.com/spadgett/origin-web-catalog/wiki/Running-the-catalog-with-the-%22UPS%22-sample-broker

Running template broker: https://github.com/spadgett/origin-web-catalog/wiki/Running-the-Catalog-with-the-Template-Broker

== Apply image-stream updates (nodejs) ==

  oc apply -f https://raw.githubusercontent.com/openshift/origin/master/examples/image-streams/image-streams-rhel7.json -n openshift

== Apply image-stream updates (java-s2i) ==

  oc apply -f https://raw.githubusercontent.com/jboss-openshift/application-templates/master/jboss-image-streams.json -n openshift

== Setup MLB parks sample ==

oc new-project mlbparks --displayName="MLB Parks App"

oc process -f https://raw.githubusercontent.com/sspeiche/mlbparks/summit/ose3/pipeline-buildconfig-template.json | oc create -f -

oc apply -f https://raw.githubusercontent.com/sspeiche/summit17/master/mlbparks-pipeline.json

oc start-build mlbparks-pipeline

oc process -f https://raw.githubusercontent.com/sspeiche/nationalparks/summit/ose3/pipeline-buildconfig-template.json | oc create -f -

oc apply -f https://raw.githubusercontent.com/sspeiche/summit17/master/nationalparks-pipeline.json

oc start-build nationalparks-pipeline

oc process -f https://raw.githubusercontent.com/sspeiche/parksmap-web/master/ose3/pipeline-buildconfig-template.json | oc create -f -


If need to great an admin user, first login into the web console as admin then:

  oc adm policy add-cluster-role-to-user cluster-admin admin
