MoinMoin on OpenShift
=====================

This git repository helps you get up and running quickly with Redis on OpenShift.


Quickstart
----------------------------

Create an account at http://openshift.redhat.com/

Create a Openshift application with a cartridge of your choice.

    rhc app create -a redis -t diy-0.1

Add this upstream repo

    cd redis
    git remote add upstream -m master git://github.com/EddyRespondek/redis-standalone-openshift-example.git
    git pull -s recursive -X theirs upstream master
    
Then push the repo upstream

    git push

That's it, you can now checkout your application at:

    http://redis-$yournamespace.rhcloud.com


